FROM python:3.12-slim

# Python-д .pyc бичүүлэхгүй, лог шууд гаргана
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /app

# Эхлээд сангуудыг суулгана (код өөрчлөгдөхөд энэ давхарга дахин ашиглагдана)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Код ба загвар
COPY main.py demand_model.joblib ./

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
