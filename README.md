# README
JD Store练习
推送到Heroku
现在存在的问题
- 点击“申请取消订单”出现“We're sorry, but something went wrong."画面
- 点击"以微信支付"或"以支付宝支付"按钮之后，出现“We're sorry, but something went wrong.”的画面
- 在“Admin 选项”里点击“取消订单”出现“we're sorry, but something went wrong"画面

在terminal输入`hekroku log`,如下

```
MJ@MJdeMacBook-Pro ⮀ ~/Project/jdstore3 ⮀ ⭠ qiniu ⮀ heroku logs
WARNING: This is the legacy Heroku CLI with limited functionality. Please install the latest CLI.
WARNING: On MacOS this can be done with 'brew install heroku' or with the MacOS package from https://cli.heroku.com
2017-07-13T15:40:22.761028+00:00 app[web.1]: I, [2017-07-13T15:40:22.760949 #4]  INFO -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   Rendered products/index.html.erb within layouts/application (5.6ms)
2017-07-13T15:40:22.763492+00:00 app[web.1]: D, [2017-07-13T15:40:22.763415 #4] DEBUG -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   Cart Load (0.7ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:22.769665+00:00 app[web.1]: D, [2017-07-13T15:40:22.769586 #4] DEBUG -- : [932606e7-934c-4b64-8591-6ec119e6bef8]    (0.9ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:22.771540+00:00 app[web.1]: D, [2017-07-13T15:40:22.771468 #4] DEBUG -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   User Load (0.8ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:22.772539+00:00 app[web.1]: I, [2017-07-13T15:40:22.772472 #4]  INFO -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   Rendered common/_navbar.html.erb (10.6ms)
2017-07-13T15:40:22.772925+00:00 app[web.1]: I, [2017-07-13T15:40:22.772857 #4]  INFO -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   Rendered common/_flashes.html.erb (0.1ms)
2017-07-13T15:40:22.773229+00:00 app[web.1]: I, [2017-07-13T15:40:22.773161 #4]  INFO -- : [932606e7-934c-4b64-8591-6ec119e6bef8]   Rendered common/_footer.html.erb (0.1ms)
2017-07-13T15:40:22.773574+00:00 app[web.1]: I, [2017-07-13T15:40:22.773510 #4]  INFO -- : [932606e7-934c-4b64-8591-6ec119e6bef8] Completed 200 OK in 20ms (Views: 15.6ms | ActiveRecord: 3.2ms)
2017-07-13T15:40:24.540272+00:00 heroku[router]: at=info method=GET path="/products/1" host=peaceful-castle-83362.herokuapp.com request_id=001fc3a3-cb35-4d1f-8007-2e456fd38fa4 fwd="183.192.60.18" dyno=web.1 connect=1ms service=22ms status=200 bytes=3948 protocol=https
2017-07-13T15:40:24.518813+00:00 app[web.1]: I, [2017-07-13T15:40:24.518702 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4] Started GET "/products/1" for 183.192.60.18 at 2017-07-13 15:40:24 +0000
2017-07-13T15:40:24.519871+00:00 app[web.1]: I, [2017-07-13T15:40:24.519797 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4] Processing by ProductsController#show as HTML
2017-07-13T15:40:24.519960+00:00 app[web.1]: I, [2017-07-13T15:40:24.519888 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Parameters: {"id"=>"1"}
2017-07-13T15:40:24.523126+00:00 app[web.1]: D, [2017-07-13T15:40:24.523018 #4] DEBUG -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Product Load (0.7ms)  SELECT  "products".* FROM "products" WHERE "products"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:24.524191+00:00 app[web.1]: I, [2017-07-13T15:40:24.524107 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Rendering products/show.html.erb within layouts/application
2017-07-13T15:40:24.525466+00:00 app[web.1]: I, [2017-07-13T15:40:24.525386 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Rendered products/show.html.erb within layouts/application (1.1ms)
2017-07-13T15:40:24.528126+00:00 app[web.1]: D, [2017-07-13T15:40:24.528031 #4] DEBUG -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Cart Load (1.3ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:24.531596+00:00 app[web.1]: D, [2017-07-13T15:40:24.531517 #4] DEBUG -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]    (0.9ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:24.533744+00:00 app[web.1]: D, [2017-07-13T15:40:24.533655 #4] DEBUG -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   User Load (0.8ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:24.534743+00:00 app[web.1]: I, [2017-07-13T15:40:24.534651 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Rendered common/_navbar.html.erb (8.4ms)
2017-07-13T15:40:24.535133+00:00 app[web.1]: I, [2017-07-13T15:40:24.535055 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Rendered common/_flashes.html.erb (0.1ms)
2017-07-13T15:40:24.535496+00:00 app[web.1]: I, [2017-07-13T15:40:24.535407 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4]   Rendered common/_footer.html.erb (0.1ms)
2017-07-13T15:40:24.535829+00:00 app[web.1]: I, [2017-07-13T15:40:24.535749 #4]  INFO -- : [001fc3a3-cb35-4d1f-8007-2e456fd38fa4] Completed 200 OK in 16ms (Views: 8.9ms | ActiveRecord: 3.8ms)
2017-07-13T15:40:25.863310+00:00 heroku[router]: at=info method=POST path="/products/1/add_to_cart" host=peaceful-castle-83362.herokuapp.com request_id=d6f90479-8550-4373-b18d-a660f5e1dbec fwd="183.192.60.18" dyno=web.1 connect=1ms service=36ms status=302 bytes=1110 protocol=https
2017-07-13T15:40:25.834224+00:00 app[web.1]: I, [2017-07-13T15:40:25.833733 #4]  INFO -- : [d6f90479-8550-4373-b18d-a660f5e1dbec] Started POST "/products/1/add_to_cart" for 183.192.60.18 at 2017-07-13 15:40:25 +0000
2017-07-13T15:40:25.837587+00:00 app[web.1]: I, [2017-07-13T15:40:25.837507 #4]  INFO -- : [d6f90479-8550-4373-b18d-a660f5e1dbec] Processing by ProductsController#add_to_cart as HTML
2017-07-13T15:40:25.837688+00:00 app[web.1]: I, [2017-07-13T15:40:25.837614 #4]  INFO -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]   Parameters: {"authenticity_token"=>"wIl2gp/Sn3cTivTS4RJrk0kdaE37B5w+9dhxfKSP/hmGr84sSC58y6NY7IF7lzG5R4A3mw0Mj8xRq1A487/izg==", "id"=>"1"}
2017-07-13T15:40:25.841634+00:00 app[web.1]: D, [2017-07-13T15:40:25.841554 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]   Product Load (1.2ms)  SELECT  "products".* FROM "products" WHERE "products"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:25.843092+00:00 app[web.1]: D, [2017-07-13T15:40:25.843022 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]   Cart Load (0.7ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:25.846933+00:00 app[web.1]: D, [2017-07-13T15:40:25.846839 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]   Product Exists (0.9ms)  SELECT  1 AS one FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1 AND "products"."id" = $2 LIMIT $3  [["cart_id", 7], ["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:25.853099+00:00 app[web.1]: D, [2017-07-13T15:40:25.853020 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]    (3.6ms)  BEGIN
2017-07-13T15:40:25.856607+00:00 app[web.1]: D, [2017-07-13T15:40:25.856534 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]   SQL (0.9ms)  INSERT INTO "cart_items" ("cart_id", "product_id", "created_at", "updated_at") VALUES ($1, $2, $3, $4) RETURNING "id"  [["cart_id", 7], ["product_id", 1], ["created_at", "2017-07-13 15:40:25.853873"], ["updated_at", "2017-07-13 15:40:25.853873"]]
2017-07-13T15:40:25.858886+00:00 app[web.1]: D, [2017-07-13T15:40:25.858814 #4] DEBUG -- : [d6f90479-8550-4373-b18d-a660f5e1dbec]    (1.6ms)  COMMIT
2017-07-13T15:40:25.859780+00:00 app[web.1]: I, [2017-07-13T15:40:25.859695 #4]  INFO -- : [d6f90479-8550-4373-b18d-a660f5e1dbec] Redirected to https://peaceful-castle-83362.herokuapp.com/products/1
2017-07-13T15:40:25.860253+00:00 app[web.1]: I, [2017-07-13T15:40:25.860185 #4]  INFO -- : [d6f90479-8550-4373-b18d-a660f5e1dbec] Completed 302 Found in 22ms (ActiveRecord: 8.9ms)
2017-07-13T15:40:26.116927+00:00 app[web.1]: I, [2017-07-13T15:40:26.116801 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d] Started GET "/products/1" for 183.192.60.18 at 2017-07-13 15:40:26 +0000
2017-07-13T15:40:26.118498+00:00 app[web.1]: I, [2017-07-13T15:40:26.118412 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d] Processing by ProductsController#show as HTML
2017-07-13T15:40:26.118611+00:00 app[web.1]: I, [2017-07-13T15:40:26.118546 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Parameters: {"id"=>"1"}
2017-07-13T15:40:26.122559+00:00 app[web.1]: D, [2017-07-13T15:40:26.122430 #4] DEBUG -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Product Load (0.9ms)  SELECT  "products".* FROM "products" WHERE "products"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:26.124543+00:00 app[web.1]: I, [2017-07-13T15:40:26.124427 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Rendering products/show.html.erb within layouts/application
2017-07-13T15:40:26.126671+00:00 app[web.1]: I, [2017-07-13T15:40:26.126214 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Rendered products/show.html.erb within layouts/application (1.5ms)
2017-07-13T15:40:26.132987+00:00 app[web.1]: D, [2017-07-13T15:40:26.132882 #4] DEBUG -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Cart Load (4.6ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:26.140909+00:00 app[web.1]: D, [2017-07-13T15:40:26.140814 #4] DEBUG -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]    (5.8ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:26.142698+00:00 app[web.1]: D, [2017-07-13T15:40:26.142618 #4] DEBUG -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   User Load (0.8ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:26.143728+00:00 app[web.1]: I, [2017-07-13T15:40:26.143649 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Rendered common/_navbar.html.erb (15.8ms)
2017-07-13T15:40:26.144206+00:00 app[web.1]: I, [2017-07-13T15:40:26.144074 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Rendered common/_flashes.html.erb (0.2ms)
2017-07-13T15:40:26.145297+00:00 app[web.1]: I, [2017-07-13T15:40:26.144476 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d]   Rendered common/_footer.html.erb (0.1ms)
2017-07-13T15:40:26.145298+00:00 app[web.1]: I, [2017-07-13T15:40:26.144865 #4]  INFO -- : [b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d] Completed 200 OK in 26ms (Views: 10.1ms | ActiveRecord: 12.1ms)
2017-07-13T15:40:26.149420+00:00 heroku[router]: at=info method=GET path="/products/1" host=peaceful-castle-83362.herokuapp.com request_id=b9e55dd3-d635-4b4e-86d6-e0e8a7b1857d fwd="183.192.60.18" dyno=web.1 connect=1ms service=33ms status=200 bytes=4118 protocol=https
2017-07-13T15:40:28.618931+00:00 heroku[router]: at=info method=GET path="/admin/products" host=peaceful-castle-83362.herokuapp.com request_id=4c6e5118-b848-4b2f-9a00-4ea6d507f7e9 fwd="183.192.60.18" dyno=web.1 connect=5ms service=28ms status=200 bytes=4265 protocol=https
2017-07-13T15:40:28.591375+00:00 app[web.1]: I, [2017-07-13T15:40:28.591274 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9] Started GET "/admin/products" for 183.192.60.18 at 2017-07-13 15:40:28 +0000
2017-07-13T15:40:28.598975+00:00 app[web.1]: D, [2017-07-13T15:40:28.598902 #4] DEBUG -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   User Load (0.9ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:28.594071+00:00 app[web.1]: I, [2017-07-13T15:40:28.593999 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9] Processing by Admin::ProductsController#index as HTML
2017-07-13T15:40:28.601168+00:00 app[web.1]: I, [2017-07-13T15:40:28.601081 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   Rendering admin/products/index.html.erb within layouts/admin
2017-07-13T15:40:28.606673+00:00 app[web.1]: D, [2017-07-13T15:40:28.603480 #4] DEBUG -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   Product Load (0.9ms)  SELECT "products".* FROM "products"
2017-07-13T15:40:28.606675+00:00 app[web.1]: I, [2017-07-13T15:40:28.604825 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   Rendered admin/products/index.html.erb within layouts/admin (3.6ms)
2017-07-13T15:40:28.607469+00:00 app[web.1]: D, [2017-07-13T15:40:28.607396 #4] DEBUG -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   Cart Load (0.8ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:28.610489+00:00 app[web.1]: D, [2017-07-13T15:40:28.610349 #4] DEBUG -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]    (1.0ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:28.611156+00:00 app[web.1]: I, [2017-07-13T15:40:28.611080 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9]   Rendered common/_navbar.html.erb (4.9ms)
2017-07-13T15:40:28.613351+00:00 app[web.1]: I, [2017-07-13T15:40:28.613273 #4]  INFO -- : [4c6e5118-b848-4b2f-9a00-4ea6d507f7e9] Completed 200 OK in 19ms (Views: 10.4ms | ActiveRecord: 3.5ms)
2017-07-13T15:40:28.913451+00:00 heroku[router]: at=info method=GET path="/admin/products" host=peaceful-castle-83362.herokuapp.com request_id=2761f2c6-20fb-4f5f-9784-10c311ae281f fwd="183.192.60.18" dyno=web.1 connect=9ms service=25ms status=200 bytes=4265 protocol=https
2017-07-13T15:40:28.889649+00:00 app[web.1]: I, [2017-07-13T15:40:28.889545 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f] Started GET "/admin/products" for 183.192.60.18 at 2017-07-13 15:40:28 +0000
2017-07-13T15:40:28.890635+00:00 app[web.1]: I, [2017-07-13T15:40:28.890565 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f] Processing by Admin::ProductsController#index as HTML
2017-07-13T15:40:28.894218+00:00 app[web.1]: D, [2017-07-13T15:40:28.894141 #4] DEBUG -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   User Load (0.9ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:28.895498+00:00 app[web.1]: I, [2017-07-13T15:40:28.895433 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   Rendering admin/products/index.html.erb within layouts/admin
2017-07-13T15:40:28.896852+00:00 app[web.1]: D, [2017-07-13T15:40:28.896764 #4] DEBUG -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   Product Load (0.8ms)  SELECT "products".* FROM "products"
2017-07-13T15:40:28.898039+00:00 app[web.1]: I, [2017-07-13T15:40:28.897970 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   Rendered admin/products/index.html.erb within layouts/admin (2.4ms)
2017-07-13T15:40:28.900097+00:00 app[web.1]: D, [2017-07-13T15:40:28.900023 #4] DEBUG -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   Cart Load (1.0ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:28.902596+00:00 app[web.1]: D, [2017-07-13T15:40:28.902532 #4] DEBUG -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]    (0.9ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:28.902984+00:00 app[web.1]: I, [2017-07-13T15:40:28.902922 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f]   Rendered common/_navbar.html.erb (4.3ms)
2017-07-13T15:40:28.903511+00:00 app[web.1]: I, [2017-07-13T15:40:28.903448 #4]  INFO -- : [2761f2c6-20fb-4f5f-9784-10c311ae281f] Completed 200 OK in 13ms (Views: 5.7ms | ActiveRecord: 3.6ms)
2017-07-13T15:40:29.208718+00:00 heroku[router]: at=info method=GET path="/assets/application-96b3ac099571efcb6bedb8a8715417d1d769af5f2d525e5e9f0f4ebdc1638070.js" host=peaceful-castle-83362.herokuapp.com request_id=4ce7d0a6-6059-4367-9b22-70c0f5d81289 fwd="183.192.60.18" dyno=web.1 connect=15ms service=16ms status=304 bytes=48 protocol=https
2017-07-13T15:40:29.173838+00:00 heroku[router]: at=info method=GET path="/assets/application-cec481318c6c7c23937bea689fa0e4f3147d66f9f165de07aff09253a3a7129f.css" host=peaceful-castle-83362.herokuapp.com request_id=c383486d-4a93-40a1-b606-0e614c52c99f fwd="183.192.60.18" dyno=web.1 connect=1ms service=1ms status=304 bytes=48 protocol=https
2017-07-13T15:40:29.512523+00:00 heroku[router]: at=info method=GET path="/assets/fontawesome-webfont-2adefcbc041e7d18fcf2d417879dc5a09997aa64d675b7a3c4b6ce33da13f3fe.woff2" host=peaceful-castle-83362.herokuapp.com request_id=f4f18cd5-6590-47ad-a16c-7fdcf5b38562 fwd="183.192.60.18" dyno=web.1 connect=18ms service=16ms status=304 bytes=48 protocol=https
2017-07-13T15:40:31.301615+00:00 heroku[router]: at=info method=GET path="/admin/orders" host=peaceful-castle-83362.herokuapp.com request_id=ded5163c-5d09-4c49-a129-26c617413548 fwd="183.192.60.18" dyno=web.1 connect=25ms service=53ms status=200 bytes=4185 protocol=https
2017-07-13T15:40:31.254094+00:00 app[web.1]: I, [2017-07-13T15:40:31.254001 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548] Processing by Admin::OrdersController#index as HTML
2017-07-13T15:40:31.249944+00:00 app[web.1]: I, [2017-07-13T15:40:31.249825 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548] Started GET "/admin/orders" for 183.192.60.18 at 2017-07-13 15:40:31 +0000
2017-07-13T15:40:31.258747+00:00 app[web.1]: D, [2017-07-13T15:40:31.258659 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   User Load (1.1ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:31.261328+00:00 app[web.1]: I, [2017-07-13T15:40:31.261262 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548]   Rendering admin/orders/index.html.erb within layouts/admin
2017-07-13T15:40:31.263376+00:00 app[web.1]: D, [2017-07-13T15:40:31.263303 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   Order Load (0.9ms)  SELECT "orders".* FROM "orders" ORDER BY id DESC
2017-07-13T15:40:31.268207+00:00 app[web.1]: D, [2017-07-13T15:40:31.268137 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   User Load (0.8ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:31.269513+00:00 app[web.1]: D, [2017-07-13T15:40:31.269444 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   CACHE (0.0ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:31.270472+00:00 app[web.1]: D, [2017-07-13T15:40:31.270410 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   CACHE (0.0ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:31.270772+00:00 app[web.1]: I, [2017-07-13T15:40:31.270711 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548]   Rendered admin/orders/index.html.erb within layouts/admin (9.3ms)
2017-07-13T15:40:31.275548+00:00 app[web.1]: D, [2017-07-13T15:40:31.275466 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]    (0.9ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:31.272623+00:00 app[web.1]: D, [2017-07-13T15:40:31.272520 #4] DEBUG -- : [ded5163c-5d09-4c49-a129-26c617413548]   Cart Load (0.7ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:31.276224+00:00 app[web.1]: I, [2017-07-13T15:40:31.276144 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548]   Rendered common/_navbar.html.erb (4.6ms)
2017-07-13T15:40:31.276936+00:00 app[web.1]: I, [2017-07-13T15:40:31.276854 #4]  INFO -- : [ded5163c-5d09-4c49-a129-26c617413548] Completed 200 OK in 23ms (Views: 13.1ms | ActiveRecord: 4.4ms)
2017-07-13T15:40:35.446510+00:00 heroku[router]: at=info method=GET path="/admin/orders/2" host=peaceful-castle-83362.herokuapp.com request_id=168d51e6-ec2a-40c4-a031-c5b3af545764 fwd="183.192.60.18" dyno=web.1 connect=1ms service=30ms status=200 bytes=4543 protocol=https
2017-07-13T15:40:35.416468+00:00 app[web.1]: I, [2017-07-13T15:40:35.416340 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764] Started GET "/admin/orders/2" for 183.192.60.18 at 2017-07-13 15:40:35 +0000
2017-07-13T15:40:35.417764+00:00 app[web.1]: I, [2017-07-13T15:40:35.417684 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764] Processing by Admin::OrdersController#show as HTML
2017-07-13T15:40:35.417842+00:00 app[web.1]: I, [2017-07-13T15:40:35.417772 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Parameters: {"id"=>"2"}
2017-07-13T15:40:35.423644+00:00 app[web.1]: D, [2017-07-13T15:40:35.423574 #4] DEBUG -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   User Load (2.9ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = $1 ORDER BY "users"."id" ASC LIMIT $2  [["id", 1], ["LIMIT", 1]]
2017-07-13T15:40:35.426466+00:00 app[web.1]: D, [2017-07-13T15:40:35.426401 #4] DEBUG -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Order Load (0.8ms)  SELECT  "orders".* FROM "orders" WHERE "orders"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
2017-07-13T15:40:35.428184+00:00 app[web.1]: I, [2017-07-13T15:40:35.428105 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Rendering admin/orders/show.html.erb within layouts/admin
2017-07-13T15:40:35.431577+00:00 app[web.1]: I, [2017-07-13T15:40:35.431503 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Rendered admin/orders/_state_option.html.erb (1.7ms)
2017-07-13T15:40:35.436660+00:00 app[web.1]: D, [2017-07-13T15:40:35.436551 #4] DEBUG -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   ProductList Load (0.8ms)  SELECT "product_lists".* FROM "product_lists" WHERE "product_lists"."order_id" = $1  [["order_id", 2]]
2017-07-13T15:40:35.437040+00:00 app[web.1]: I, [2017-07-13T15:40:35.436981 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Rendered admin/orders/show.html.erb within layouts/admin (8.7ms)
2017-07-13T15:40:35.439140+00:00 app[web.1]: D, [2017-07-13T15:40:35.439081 #4] DEBUG -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Cart Load (0.7ms)  SELECT  "carts".* FROM "carts" WHERE "carts"."id" = $1 LIMIT $2  [["id", 7], ["LIMIT", 1]]
2017-07-13T15:40:35.442344+00:00 app[web.1]: D, [2017-07-13T15:40:35.442265 #4] DEBUG -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]    (1.1ms)  SELECT COUNT(*) FROM "products" INNER JOIN "cart_items" ON "products"."id" = "cart_items"."product_id" WHERE "cart_items"."cart_id" = $1  [["cart_id", 7]]
2017-07-13T15:40:35.442824+00:00 app[web.1]: I, [2017-07-13T15:40:35.442769 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764]   Rendered common/_navbar.html.erb (4.8ms)
2017-07-13T15:40:35.443357+00:00 app[web.1]: I, [2017-07-13T15:40:35.443281 #4]  INFO -- : [168d51e6-ec2a-40c4-a031-c5b3af545764] Completed 200 OK in 25ms (Views: 12.9ms | ActiveRecord: 6.2ms)
```
