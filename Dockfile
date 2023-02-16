FROM python:3.8-slim-buster

# kivyの依存ライブラリをインストール
RUN apt-get update && \
    apt-get install -y \
        libsdl2-dev \
        libsdl2-image-dev \
        libsdl2-mixer-dev \
        libsdl2-ttf-dev \
        libportmidi-dev \
        libswscale-dev \
        libavformat-dev \
        libavcodec-dev \
        zlib1g-dev

# 作業ディレクトリを設定
WORKDIR /app

# 必要なPythonパッケージをインストール
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# ホスト側のカレントディレクトリにあるファイルを、コンテナ内の/appディレクトリにコピー
COPY . .

# ポート番号を設定
EXPOSE 8000

# コンテナが起動した時に実行されるコマンドを設定
CMD ["python", "main.py"]
