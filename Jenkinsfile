pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                sh "git clone https://github.com/ScastellanosM/movie-analyst-ui.git"
                sh "rm -rf movie-analyst-ui"
            }
        }
        stage('Build'){
            steps {
                sh "zip -r movie-analyst-ui.zip /var/lib/jenkins/workspace/FrontA_master"      
            }
        }
        stage('Deploy'){
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'ubuntu', keyFileVariable: 'MIIEpAIBAAKCAQEAqOprxIpinGk+z5KOnFK/IqV1gzqeAWXKcsTPAgFNFLLM3eEaAAcu6mQDXINy
uUNlDq/n0p42iy6ciZQprjcJ16Y02/0Pz0ZQq70L8EotlL9DBjah/LPSjgDCiAFkMkBl5UmJuCkL
vYPfPV4RNvv0k6Uv8B5r0SW2oH5iyTxLhtoSvcCrRRv2ZGE90jvBL0cUmVZkuFrQzdNhC8XhoMWJ
H4GjQAp2WJOfV+Ev7AozU/zpVz6U9i+4P2D7vVniA1lNa18POGbOqgBN2eEdeBUa2GQBENAtS8bX
l9yxhSes/yWzsWAaYJQc7D8MXOjHVlCrguxFMBHT4aH4kaJ8owwMJQIDAQABAoIBAEshAM/I8TU6
RlqSh+WVlDe3uf2lK7PZb2L+kEgHBh6nrCEfxq2uhDpyQ2B5gqROCnuu14BBKGddUviKMsOu7SzC
Ww5hjw+U6bqI+e9lPsLDEu+HiyLXZFYOlndhjwwewnNp8tw7PWKMbdVgqm13QQAOX7UAAtpiWMkn
jY6Nx9XxHSKigyjd5tz3nEk2B9aiohv4cxzBNBqnnRSwH6YFu8N/Vqv+ebA0NKyzF2KgiOXFVypi
auMmb55NQysayeR112RONDfCRWHzdt3wzC8RP2EMCuEY8cj/yxNcEgr8yY/cbVZVfR9BR+SzGKwO
C/MTzaP+cCta5+pRfdSTwR4AW50CgYEA31ipldVtGe95v1tD06XDBBCvYB578niHSH3eYJpcii4a
u2XqQ0d5IXBPoDkIHzIirsyUkDS8VY1puIkFs/mlY4aQXLUoR7qw/d2+ky+bqrW6n80/fD9NCBFi
U/9M7PROrko9xTTzJ2TrQKfvvOrC5POutPYskXp8qNtOuoDNPlsCgYEAwZyLtTZXgR7FP7uwPrdm
bQ9+Ub6R2Pfl8wzw2rgTdOFxfu8P1y3At/Ldaipcy//KvunRJp2oyzDz2c2HzZzxb6P/E0c2Ofae
QDVCTiRZKtbUhSFZq6XkPqGCVhVnw+1iNm29dA1DpOWiLQqoMHb0o2e1vb0a2Pwr+dhxISvC538C
gYBBcxT3IH0BPakax17f9dJpLY6HB0fhLSrPtnrlKjb2Ez6oLdxxbM91WhkrZasYoTOCr9bVT27l
TzRs7FJshDrQKI3DbR7pri7RphqDvU7Lvsd6rsXs3gvv0lBTNxxOz+UCtCTX1oVuxOcfolbhsJX+
S96ljwJOe2tufB3dD4OVwwKBgQCxPrxTqC0RovbW8t9VexbEzwNImJrys3eLO5Sf1xbQ0LbTis3I
ozUj8a2rzJ5pj4Gvp2R24qytX+JNybAClyQcnVkd7/p/s/uKMnfCC9qpskSaoD50OomqoLcuUahO
INrhkzN2s9HyetsuOuxgefZaRc6GpkGW1bz4nKJsyKBExwKBgQCVRs/bgG2D84XTvm81nCTVdfzy
NVlTbgQq1VJc1ywEB9P+GxH/YLNZr7ddgfadlXqJrlZKC7a5ZErbmufz/zYdl2pz61FjDOaRSmqU
dbJxuuHjgWK9Z6lK7XKTjbvsekZId4DrPLlLt8vxGQAHXCydSHqSaxW9eF6yBLDTCU/05Q==')]) {
                sh "scp -i  /var/lib/jenkins/workspace/FrontA_master/movie-analyst-ui.zip ubuntu@11.0.1.17:/home/ubuntu"
             }       
           }
        }     
    }
}
  
