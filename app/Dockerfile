# Utiliza una imagen base oficial de Python
FROM python:3.9-slim


# Instalar las dependencias necesarias para psycopg2 y compilar extensiones
RUN apt-get update \
    && apt-get install -y libpq-dev gcc \
    && rm -rf /var/lib/apt/lists/*

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia el archivo requirements.txt para instalar dependencias
COPY requirements.txt .

# Instala las dependencias necesarias
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Copia el resto de los archivos de la aplicación al contenedor
COPY . .

# Expone el puerto en el que Flask correrá
EXPOSE 5000

# Define el comando para ejecutar la aplicación Flask
CMD ["python", "app.py"]
