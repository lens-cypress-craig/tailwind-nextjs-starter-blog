FROM node:22

WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# enable pnpm in case that is needed by the user
RUN corepack enable pnpm

# install app dependencies
COPY package.json yarn.lock* package-lock.json* pnpm-lock.yaml* ./

RUN yarn install

# add app to container and attempt build
COPY . ./
RUN $ EXPORT&#x3D;1 UNOPTIMIZED&#x3D;1 BASE_PATH&#x3D;&#x2F;myblog yarn build

# the start command needs to be triple curly braces to avoid escaping special characters
CMD ["yarn", "dev"]