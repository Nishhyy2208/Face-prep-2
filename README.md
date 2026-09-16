for (let i = 1; i <= 50; i++) {

    db.products.insertOne({
        productId: i,
        productName: "Product " + i ,
        category:
            i % 5 === 0 ? "Laptop" :
            i % 5 === 1 ? "Mobile" :
            i % 5 === 2 ? "Headphones" :
            i % 5 === 3 ? "Keyboard" :
                          "Mouse",

        brand:
            i % 3 === 0 ? "Dell" :
            i % 3 === 1 ? "Samsung" :
                          "HP",

        price: 1000 + (i * 500),

        stock: 10 + i,

        rating: 3 + ((i % 3) * 0.5),

        inStock: i % 4 !== 0,

        tags: [
            "electronics",
            i % 2 === 0 ? "featured" : "new"
        ],

        seller: {
            sellerId: 1000 + i,
            sellerName: "Seller " + i
        },

        createdAt: new Date()
    });
}
