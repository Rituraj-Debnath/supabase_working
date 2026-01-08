when i setup self hosted supabase , i created from scratch , before doing compose up i changes these values that were must like : JWT_SECRET , ANON_KEY , SERVICE_ROLE_KEY,,,,,,,,,,,,


### first generating Jwt secret ####
openssl rand -hex 32
and then pasted it in the env.
#### installed npm and ndoejs latest using nvm #######
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
source ~/.bashrc
then : nvm install node


-------- getting the .env in shell --------
set -a
source .env
set +a

then: echo $JWT_SECRET

ANON key = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlzcyI6InN1cGFiYXNlIiwiYXVkIjoiYXV0aGVudGljYXRlZCIsImlhdCI6MTc2Nzg5ODg5NCwiZXhwIjoyMDgzNDc0ODk0fQ.lR1sEVPfa5ySMS1L1p3M8uEand3_6WNpVM8cFeJnKVA

service role key : eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoic2VydmljZV9yb2xlIiwiaXNzIjoic3VwYWJhc2UiLCJhdWQiOiJhdXRoZW50aWNhdGVkIiwiaWF0IjoxNzY3ODk4ODk0LCJleHAiOjIwODM0NzQ4OTR9.uJ7mEE8tbnfu3nc-1HH0dd8qx1O1PxYcM0-69cnuL0E



#### generating anon key command 
docker run --rm supabase/gotrue:latest \
  gotrue key generate \
  --jwt-secret "YOUR_JWT_SECRET" \
  --role anon


#### generating service role key #######
docker run --rm supabase/gotrue:latest \
  gotrue key generate \
  --jwt-secret "YOUR_JWT_SECRET" \
  --role service_role

how about these-------------how to get them,,are they mandatory before doing compose up ? 


-----phase 2 that i changed ------
URLs & Issuer (Auth correctness)

SITE_URL
API_EXTERNAL_URL
SUPABASE_PUBLIC_URL



