# Ubuntuの最新版をベースイメージとして使用
FROM ubuntu:latest

# 環境を更新し必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    wget \
    apt-transport-https \
    software-properties-common \
    # PowerShellの公式リポジトリを追加
    && wget -q "https://packages.microsoft.com/config/ubuntu/$(. /etc/os-release && echo $VERSION_ID)/packages-microsoft-prod.deb" -O packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && apt-get update \
    # PowerShellをインストール
    && apt-get install -y powershell \
    # 不要なパッケージを削除し、キャッシュをクリア
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -f packages-microsoft-prod.deb

# PowerShellをデフォルトのシェルとして設定
ENTRYPOINT ["pwsh"]
