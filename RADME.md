<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Alpha Nutrition | Premium Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@900&family=Inter:wght@400;600;700&display=swap');
        body { background-color: #000; color: #fff; font-family: 'Inter', sans-serif; overflow-x: hidden; }
        .gold-text { color: #D4AF37; }
        .gold-bg { background: linear-gradient(135deg, #D4AF37 0%, #B8860B 100%); }
        .alpha-font { font-family: 'Montserrat', sans-serif; }
        .product-card { background: #111; border: 1px solid #222; }
        #sidebar { transition: transform 0.3s ease-in-out; }
    </style>
</head>
<body class="pb-20">

    <nav class="bg-black border-b border-zinc-900 sticky top-0 z-50">
        <div class="p-4 flex items-center gap-4">
            <button onclick="toggleMenu()" class="text-white text-2xl">☰</button>
            
            <div class="flex-grow">
                <h1 class="alpha-font text-xl italic font-black tracking-tighter uppercase leading-none">ALPHA<span class="gold-text">NUTRITION</span></h1>
            </div>

            <div class="flex gap-4 text-zinc-400">
                <span>👤</span>
                <span>🛒</span>
            </div>
        </div>

        <div class="px-4 pb-3">
            <div class="bg-zinc-900 rounded-lg flex items-center px-3 py-2 border border-zinc-800">
                <span class="text-zinc-500 mr-2">🔍</span>
                <input type="text" placeholder="Search for brands, proteins..." class="bg-transparent text-sm w-full outline-none text-white">
            </div>
        </div>

        <div class="flex overflow-x-auto gap-6 px-4 py-3 text-[10px] font-bold uppercase tracking-widest border-t border-zinc-900 no-scrollbar">
            <a href="#" class="gold-text whitespace-nowrap text-white">All Products</a>
            <a href="#" class="whitespace-nowrap text-zinc-400">Whey</a>
            <a href="#" class="whitespace-nowrap text-zinc-400">Creatine</a>
            <a href="#" class="whitespace-nowrap text-zinc-400">Pre-Workout</a>
            <a href="#" class="whitespace-nowrap text-zinc-400">Gainer</a>
        </div>
    </nav>

    <div id="sidebar" class="fixed top-0 left-0 h-full w-72 bg-zinc-950 z-[60] -translate-x-full border-r border-zinc-800 shadow-2xl">
        <div class="p-6 border-b border-zinc-900 flex justify-between items-center">
            <h2 class="gold-text font-black italic tracking-tighter">MENU</h2>
            <button onclick="toggleMenu()" class="text-2xl">✕</button>
        </div>
        <div class="p-4 space-y-6">
            <div class="space-y-4">
                <p class="text-zinc-500 text-[10px] uppercase font-bold tracking-widest">Categories</p>
                <a href="#" class="block text-lg font-semibold">Whey Protein</a>
                <a href="#" class="block text-lg font-semibold">Mass Gainers</a>
                <a href="#" class="block text-lg font-semibold">Pre-Workouts</a>
                <a href="#" class="block text-lg font-semibold">Fat Burners</a>
            </div>
            <hr class="border-zinc-900">
            <div class="space-y-4">
                <p class="text-zinc-500 text-[10px] uppercase font-bold tracking-widest">Support</p>
                <a href="#" class="block text-zinc-400">My Orders</a>
                <a href="#" class="block text-zinc-400">Contact Us</a>
                <a href="#" class="block text-zinc-400">Privacy Policy</a>
            </div>
        </div>
    </div>

    <div id="overlay" onclick="toggleMenu()" class="fixed inset-0 bg-black/80 z-[55] hidden"></div>

    <main class="p-4 space-y-4">
        <div class="gold-bg rounded-2xl p-6 h-32 flex items-center justify-between">
            <div>
                <h2 class="text-black font-black text-2xl italic leading-none">GRAND<br>OPENING</h2>
                <p class="text-black/70 text-[10px] font-bold uppercase mt-1">Flat 20% Off</p>
            </div>
            <span class="text-4xl">🔥</span>
        </div>

        <div class="grid grid-cols-1 gap-4">
            <div class="product-card rounded-2xl p-4 flex gap-4 items-center">
                <div class="w-24 h-24 bg-zinc-900 rounded-xl flex items-center justify-center font-black text-zinc-700 italic">WHEY</div>
                <div class="flex-grow">
                    <h3 class="font-bold text-sm uppercase italic leading-tight">Premium Whey Isolate</h3>
                    <p class="gold-text font-black mt-1 text-lg">₹4,999</p>
                    <button onclick="sendOrder('Whey Protein', '₹4,999')" class="mt-2 text-[10px] font-bold border border-zinc-700 px-3 py-1 rounded-full">BUY NOW</button>
                </div>
            </div>
        </div>
    </main>

    <footer class="p-10 text-center border-t border-zinc-900 bg-zinc-950">
        <p class="text-zinc-500 text-[10px] uppercase tracking-widest mb-3">Founders</p>
        <div class="flex justify-center gap-4 mb-6">
            <p class="text-white font-bold text-lg uppercase italic tracking-tighter">Soumya</p>
            <p class="gold-text font-black text-lg">×</p>
            <p class="text-white font-bold text-lg uppercase italic tracking-tighter">Som</p>
        </div>
        <p class="gold-text font-bold text-sm">+91 8653320872</p>
    </footer>

    <script>
        function toggleMenu() {
            const sidebar = document.getElementById('sidebar');
            const overlay = document.getElementById('overlay');
            if (sidebar.style.transform === 'translateX(0px)') {
                sidebar.style.transform = 'translateX(-100%)';
                overlay.classList.add('hidden');
            } else {
                sidebar.style.transform = 'translateX(0px)';
                overlay.classList.remove('hidden');
            }
        }

        function sendOrder(name, price) {
            const phone = "918653320872";
            const message = `Hello Alpha Nutrition! I want to order:\n\n*Product:* ${name}\n*Price:* ${price}`;
            window.location.href = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`;
        }
    </script>
</body>
</html>import React, { useState, useEffect } from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button";

// =============================== // ALPHA NUTRITION - FLIPKART LEVEL E-COMMERCE (SINGLE FILE DEMO) // Features: Auth, Admin Panel, Products CRUD, Cart, Orders, LocalStorage // ===============================

const initialProducts = [ { id: 1, name: "Whey Protein", price: 2499, desc: "Muscle growth & recovery" }, { id: 2, name: "Creatine", price: 999, desc: "Strength & power boost" }, { id: 3, name: "Pre Workout", price: 1299, desc: "Explosive energy" }, { id: 4, name: "Multivitamin", price: 699, desc: "Health & immunity" } ];

export default function App() { // ================= USER ================= const [user, setUser] = useState(null); const [login, setLogin] = useState({ email: "", pass: "" });

// ================= DATA ================= const [products, setProducts] = useState(initialProducts); const [cart, setCart] = useState([]); const [orders, setOrders] = useState([]);

// ================= UI STATE ================= const [page, setPage] = useState("shop"); // shop | cart | admin | orders

// ================= ADMIN FORM ================= const [newProduct, setNewProduct] = useState({ name: "", price: "", desc: "" });

// ================= LOCAL STORAGE ================= useEffect(() => { const saved = localStorage.getItem("alpha_data"); if (saved) { const data = JSON.parse(saved); setProducts(data.products || initialProducts); setOrders(data.orders || []); } }, []);

useEffect(() => { localStorage.setItem("alpha_data", JSON.stringify({ products, orders })); }, [products, orders]);

// ================= AUTH ================= const handleLogin = () => { if (login.email && login.pass) setUser(login.email); else alert("Enter login details"); };

const logout = () => setUser(null);

// ================= CART ================= const addToCart = (p) => setCart([...cart, p]); const removeCart = (i) => { const c = [...cart]; c.splice(i, 1); setCart(c); };

const total = cart.reduce((a, b) => a + b.price, 0);

// ================= ORDER ================= const placeOrder = () => { const newOrder = { id: Date.now(), items: cart, total }; setOrders([...orders, newOrder]); setCart([]); alert("Order placed successfully!"); };

// ================= ADMIN ================= const addProduct = () => { if (!newProduct.name || !newProduct.price) return; setProducts([ ...products, { id: Date.now(), ...newProduct, price: Number(newProduct.price) } ]); setNewProduct({ name: "", price: "", desc: "" }); };

const deleteProduct = (id) => { setProducts(products.filter(p => p.id !== id)); };

// ================= LOGIN SCREEN ================= if (!user) { return ( <div className="min-h-screen flex items-center justify-center bg-black text-white"> <div className="bg-gray-900 p-6 rounded-xl w-80"> <h1 className="text-green-400 text-2xl font-bold mb-4">Alpha Nutrition</h1> <input className="w-full p-2 mb-2 text-black" placeholder="Email" onChange={e => setLogin({ ...login, email: e.target.value })} /> <input className="w-full p-2 mb-4 text-black" placeholder="Password" type="password" onChange={e => setLogin({ ...login, pass: e.target.value })} /> <Button className="w-full" onClick={handleLogin}>Login</Button> </div> </div> ); }

// ================= MAIN ================= return ( <div className="min-h-screen bg-black text-white p-4">

{/* HEADER */}
  <div className="flex justify-between items-center">
    <h1 className="text-green-400 font-bold text-xl">Alpha Nutrition</h1>
    <div className="flex gap-2 flex-wrap">
      <Button onClick={() => setPage("shop")}>Shop</Button>
      <Button onClick={() => setPage("cart")}>Cart ({cart.length})</Button>
      <Button onClick={() => setPage("orders")}>Orders</Button>
      <Button onClick={() => setPage("admin")}>Admin</Button>
      <Button onClick={logout}>Logout</Button>
    </div>
  </div>

  {/* ================= SHOP ================= */}
  {page === "shop" && (
    <div className="grid md:grid-cols-2 gap-4 mt-4">
      {products.map(p => (
        <Card key={p.id} className="bg-gray-900">
          <CardContent>
            <h2 className="text-green-400 font-bold text-xl">{p.name}</h2>
            <p>{p.desc}</p>
            <p className="font-bold mt-2">₹{p.price}</p>
            <Button className="mt-2" onClick={() => addToCart(p)}>Add</Button>
          </CardContent>
        </Card>
      ))}
    </div>
  )}

  {/* ================= CART ================= */}
  {page === "cart" && (
    <div className="bg-gray-900 p-4 mt-4 rounded">
      <h2 className="text-xl font-bold">Cart</h2>
      {cart.map((c, i) => (
        <div key={i} className="flex justify-between border-b py-2">
          <span>{c.name}</span>
          <span>₹{c.price}</span>
          <button onClick={() => removeCart(i)} className="text-red-400">X</button>
        </div>
      ))}
      <p className="mt-2 font-bold">Total: ₹{total}</p>
      <Button className="mt-3 w-full" onClick={placeOrder}>Place Order</Button>
    </div>
  )}

  {/* ================= ORDERS ================= */}
  {page === "orders" && (
    <div className="mt-4 bg-gray-900 p-4 rounded">
      <h2 className="text-xl font-bold">Orders</h2>
      {orders.length === 0 && <p>No orders yet</p>}
      {orders.map(o => (
        <div key={o.id} className="border-b py-2">
          <p>Order ID: {o.id}</p>
          <p>Total: ₹{o.total}</p>
        </div>
      ))}
    </div>
  )}

  {/* ================= ADMIN PANEL ================= */}
  {page === "admin" && (
    <div className="mt-4 bg-gray-900 p-4 rounded">
      <h2 className="text-xl font-bold">Admin Panel</h2>

      <input className="w-full p-2 text-black mt-2" placeholder="Product Name"
        value={newProduct.name}
        onChange={e => setNewProduct({ ...newProduct, name: e.target.value })}
      />

      <input className="w-full p-2 text-black mt-2" placeholder="Price"
        value={newProduct.price}
        onChange={e => setNewProduct({ ...newProduct, price: e.target.value })}
      />

      <input className="w-full p-2 text-black mt-2" placeholder="Description"
        value={newProduct.desc}
        onChange={e => setNewProduct({ ...newProduct, desc: e.target.value })}
      />

      <Button className="mt-2" onClick={addProduct}>Add Product</Button>

      <div className="mt-4">
        {products.map(p => (
          <div key={p.id} className="flex justify-between border-b py-2">
            <span>{p.name}</span>
            <button className="text-red-400" onClick={() => deleteProduct(p.id)}>Delete</button>
          </div>
        ))}
      </div>
    </div>
  )}

</div>

); }
