when i setup self hosted supabase , i created from scratch , before doing compose up i changes these values that were must like : JWT_SECRET , ANON_KEY , SERVICE_ROLE_KEY,,,,,,,,,,,,
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

VAULT_ENC_KEY=
PG_META_CRYPTO_KEY=
SECRET_KEY_BASE=
