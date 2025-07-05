
FROM jupyter/pyspark-notebook:latest


USER root
WORKDIR /app

# Apenas instala libpq-dev se necessário
RUN apt-get update && \
    apt-get install -y  libpq-dev gcc && \
    apt-get clean


# Copia o driver JDBC para o Spark
RUN mkdir -p /opt/spark/jars
COPY jars/postgresql-42.7.3.jar /usr/local/spark/jars/

# Instala as dependências Python
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

USER jovyan

# Inicia o Jupyter
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root", "--NotebookApp.token=", "--NotebookApp.password="]
