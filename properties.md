
# Property Resource Paths

Y - `/properties`                         - [GET, POST]
Y - `/properties/:propId`                 - [GET, PATCH, DELETE]
Y - `/properties/:propId/images`          - [GET, POST]
Y - `/properties/:propId/images/:imageId` - [GET, PATCH, DELETE]
Y - `/properties/:propId/sales`           - [GET, POST]
Y - `/properties/:propId/sales/:saleId`   - [GET, PATCH, DELETE]
Y - `/sales`                              - [GET]
Y - `/sales/:saleId`                      - [GET]
Y - `/sales/:saleId/offers`               - [GET, POST]
Y - `/sales/:saleId/offers/:offerId`      - [GET, DELETE]
Y - `/user/properties`                    - [GET]
Y - `/user/sales`                         - [GET]
Y - `/users/:username/sales`              - [GET]

Offers:

* Can only be placed on active sales.
* Can only be placed on sales of other peoples. (i.e. cannnot make an offer to buy your own property)
