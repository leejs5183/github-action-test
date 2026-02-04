name: tomcat build test

on:
  push:
    branches: [ "main" ]

jobs:
  build-and-push:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Login
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Build
        run: |
          docker build -t ${{ secrets.DOCKERHUB_USERNAME }}/mytomcat:latest .

      - name: Push
        run: |
          docker push ${{ secrets.DOCKERHUB_USERNAME }}/mytomcat:latest

