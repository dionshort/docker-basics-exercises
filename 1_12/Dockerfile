FROM ubuntu

WORKDIR /usr/src/app

RUN apt-get update && apt-get install -y curl && apt-get install -y sudo
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash
RUN sudo apt install -y nodejs

RUN npm install -g serve

COPY package.json package-lock.json ./

RUN npm install

COPY . .

RUN npm run build

EXPOSE 5001

CMD ["serve", "-s", "-l", "5001", "build"]
