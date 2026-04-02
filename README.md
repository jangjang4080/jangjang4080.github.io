# 소개
jangjang4080

## Jekyll
- https://jekyllrb-ko.github.io/docs  
- minima 테마

# 설치
1. rvm 설치: https://rvm.io
2. Ruby 설치
   ```shell
   rvm install 3.3.7
   rvm use 3.3.7 --default
   ```
3. 의존성 설치 및 실행
   ```shell
   gem install bundler
   bundle install
   bundle exec jekyll serve
   ```

### 버전 충돌 문제 생기거나, 설치 에러 시
```shell
bundle clean
bundle clean --force
```