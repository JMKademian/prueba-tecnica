#IMAGEN DE NODE.JS ULTIMA VERSION
FROM node
#ESTABLECE EL DIRECTORIO DE TRABAJO
WORKDIR /app/frontend
#COPIA LOS ARCHIVOS EN EL DIRECTORIO DE TRABAJO
COPY . .
#INSTALA DEPENDENCIAS DE LA APLICACION NPM
RUN npm install
#GENERA UNA VERSION OPTIMIZADA DE LA APP
RUN npm run build
#EXPONE EL PUERTO 3000
EXPOSE 3000
#EJECTUTA LOS SIGUIENTES COMANDOS AL INICIAR EL CONTENEDOR
CMD ["npm", "start"]
