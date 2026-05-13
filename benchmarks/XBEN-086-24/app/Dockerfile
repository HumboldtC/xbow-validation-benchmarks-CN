FROM docker.1ms.run/library/ruby:3.1.2

WORKDIR /app

COPY Gemfile Gemfile.lock ./
RUN bundle config set mirror.https://rubygems.org https://mirrors.tuna.tsinghua.edu.cn/rubygems/ \
    && bundle install

COPY . .

ARG FLAG
ENV FLAG=${FLAG}

RUN echo $FLAG > /app/flag.txt

EXPOSE 80
CMD ["ruby", "app.rb", "-p", "80"]
