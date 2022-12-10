docker build -t kurabi/query:0.0.1 .
docker build -t kurabi/posts:0.0.1 .
docker build -t kurabi/comments:0.0.1 .
docker build -t kurabi/moderation:0.0.1 .
docker build -t kurabi/event-bus:0.0.1 .
docker build -t kurabi/client:0.0.1 .

docker run --name event-bus -dp 4005:4005 kurabi/event-bus:0.0.1
docker run --name posts -dp 4000:4000 kurabi/posts:0.0.1
docker run --name comments -dp 4001:4001 kurabi/comments:0.0.1
docker run --name query -dp 4002:4002 kurabi/query:0.0.1
docker run --name moderation -dp 4003:4003 kurabi/moderation:0.0.1

docker run --name client -dp 3000:3000 kurabi/client:0.0.1
