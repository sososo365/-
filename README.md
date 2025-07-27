# -import streamlit as st
import yfinance as yf
import requests
from datetime import datetime
from bs4 import BeautifulSoup
import pandas as pd

st.set_page_config(page_title="📊 Market Sentiment Strategy", layout="centered")

# 상태 변수 (세션 저장)
if 'schd' not in st.session_state:
    st.session_state.schd = 100.0
    st.session_state.tqqq = 0.0
    st.session_state.month_counter = 0
    st.session_state.last_month = None

# 색상 대체 텍스트 표시
def sentiment_color_label(text, color):
    return f"**{text}**"
