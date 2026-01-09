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

----------- both key generation ----------

const jwt = require('jsonwebtoken')
const make = (role) =>
  jwt.sign(
    { role, iss: 'supabase', aud: 'authenticated' },
    process.env.JWT_SECRET,
    { expiresIn: '10y' }
  )

console.log('ANON_KEY:', make('anon'))
console.log('SERVICE_ROLE_KEY:', make('service_role'))


ANON key = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiYW5vbiIsImlzcyI6InN1cGFiYXNlIiwiYXVkIjoiYXV0aGVudGljYXRlZCIsImlhdCI6MTc2Nzg5ODg5NCwiZXhwIjoyMDgzNDc0ODk0fQ.lR1sEVPfa5ySMS1L1p3M8uEand3_6WNpVM8cFeJnKVA

service role key : eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoic2VydmljZV9yb2xlIiwiaXNzIjoic3VwYWJhc2UiLCJhdWQiOiJhdXRoZW50aWNhdGVkIiwiaWF0IjoxNzY3ODk4ODk0LCJleHAiOjIwODM0NzQ4OTR9.uJ7mEE8tbnfu3nc-1HH0dd8qx1O1PxYcM0-69cnuL0E




-----phase 2 that i changed ------
URLs & Issuer (Auth correctness)

SITE_URL
API_EXTERNAL_URL
SUPABASE_PUBLIC_URL


phase 3 -----------

next i changed these : 
SECRET_KEY_BASE=
VAULT_ENC_KEY=your-32-character-encryption-key
PG_META_CRYPTO_KEY=your-encryption-key-32-chars-min

using ocmmand____:  openssl rand -base64 64






