# $ gcloud iam service-accounts create github-actions
# $ gcloud iam service-accounts list
# $ gcloud iam service-accounts keys create ./private-key.json --iam-account=<EMAIL>
# $ export GKE_SA_KEY=$(cat private-key.json | base64)
# $ echo $GKE_SA_KEY
# $ git clone https://github.com/jylhakos/DevOpsWithKubernetes.git
# $ git commit -m "3.04"
# $ kubectl kustomize build . 
# $ git branch -m master main
# $ git push -u origin main
# $ git switch -c branch_3_04
# $ git add .
# $ git commit -m "3.04"
# $ git push origin branch_3_04
# $ git checkout main
# $ git fetch origin
# $ git merge branch_3_04
# $ git reset --hard origin/main

FROM node:alpine

WORKDIR /usr/src/app

RUN apk --no-cache add curl

COPY ./todo-backend-db/package*.json ./

RUN npm ci

COPY . .

EXPOSE 3002

CMD ["npm", "start"]
