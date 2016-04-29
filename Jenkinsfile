node {
  stage 'Build'
  def utils = load 'utils.groovy'
  utils.setEnv('go', '1.5')
  sh 'env'
  sh 'go get github.com/golang/lint/golint'
  sh 'go get -t -v ./...'
  sh 'OUT=`gofmt -l .`; if [ "$OUT" ]; then echo $OUT; exit 1; fi'
  sh 'OUT=`golint ./...`; if [ "$OUT" ]; then echo $OUT; exit 1; fi'
  sh 'go vet ./...'
}
