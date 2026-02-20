import React, { useState } from "react"; import { motion } from "framer-motion"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { MessageCircle } from "lucide-react";

export default function JayaKeluargaMandiriWebsite() { const phoneNumber = "6281229637820"; const displayPhone = "+62 812-2963-7820";

const [city, setCity] = useState("Jakarta"); const [form, setForm] = useState({ nama: "", telepon: "", lokasi: "", unit: "", durasi: 1 });

const prices = { "Mini Excavator": 3000000, "Excavator Standar": 5000000, "Excavator Long Arm": 7500000 };

const cities = ["Jakarta", "Bogor", "Depok", "Tangerang", "Bekasi"];

const handleChange = (e) => { setForm({ ...form, [e.target.name]: e.target.value }); };

const totalHarga = form.unit ? prices[form.unit] * form.durasi : 0;

const handleSubmit = (e) => { e.preventDefault(); const message = Halo Jaya Keluarga Mandiri, saya ingin booking:%0A Area: ${city}%0A Nama: ${form.nama}%0A Telepon: ${form.telepon}%0A Lokasi Proyek: ${form.lokasi}%0A Unit: ${form.unit}%0A Durasi: ${form.durasi} hari%0A Total Estimasi: Rp ${totalHarga.toLocaleString()}; window.open(https://wa.me/${phoneNumber}?text=${message}, "_blank"); };

return ( <div className="min-h-screen bg-gray-50 text-gray-800"> {/* SEO */} <title>Rental Excavator Jabodetabek | Jaya Keluarga Mandiri</title> <meta name="description" content="Rental excavator profesional area Jabodetabek. Sewa mini excavator, standar & long arm dengan harga terbaik. Hubungi 0812-2963-7820" />

{/* Header */}
  <div className="bg-black text-white py-4 text-center">
    <h1 className="text-2xl font-bold">JAYA KELUARGA MANDIRI</h1>
    <p className="text-sm">Spesialis Rental Excavator Jabodetabek</p>
  </div>

  {/* Area Selector */}
  <div className="bg-yellow-100 py-4 text-center">
    <span className="mr-3 font-semibold">Area Layanan:</span>
    {cities.map((c, i) => (
      <button
        key={i}
        onClick={() => setCity(c)}
        className={`mx-2 px-4 py-2 rounded-2xl ${city === c ? "bg-yellow-500 text-white" : "bg-white"}`}
      >
        {c}
      </button>
    ))}
  </div>

  {/* Hero */}
  <section className="bg-yellow-500 text-white py-20 px-6 text-center">
    <motion.h2 initial={{ opacity: 0 }} animate={{ opacity: 1 }} className="text-4xl md:text-5xl font-bold mb-4">
      Rental Excavator {city} Terpercaya
    </motion.h2>
    <p className="text-lg mb-6">
      Melayani sewa excavator untuk proyek konstruksi, cut & fill, perataan tanah, bongkaran bangunan dan tambang di wilayah {city}.
    </p>
    <Button onClick={() => window.open(`https://wa.me/${phoneNumber}`, "_blank")} className="bg-black text-white rounded-2xl px-6 py-3">
      Hubungi Sekarang ({displayPhone})
    </Button>
  </section>

  {/* Pricing */}
  <section className="py-16 px-6 max-w-6xl mx-auto">
    <h2 className="text-3xl font-bold text-center mb-12">Harga Sewa Excavator {city}</h2>
    <div className="grid md:grid-cols-3 gap-8">
      {Object.keys(prices).map((key, i) => (
        <Card key={i} className="rounded-2xl shadow-xl text-center">
          <CardContent className="p-8">
            <h3 className="text-xl font-semibold mb-4">{key}</h3>
            <p className="text-2xl font-bold mb-6">Rp {prices[key].toLocaleString()} / hari</p>
          </CardContent>
        </Card>
      ))}
    </div>
  </section>

  {/* About SEO Section */}
  <section className="py-16 px-6 bg-white">
    <div className="max-w-4xl mx-auto text-center">
      <h2 className="text-3xl font-bold mb-6">Tentang Jaya Keluarga Mandiri</h2>
      <p className="text-gray-700 leading-relaxed">
        Jaya Keluarga Mandiri adalah perusahaan rental alat berat terpercaya yang melayani area Jabodetabek.
        Kami menyediakan unit excavator terawat dengan operator berpengalaman untuk memastikan proyek Anda berjalan lancar.
        Komitmen kami adalah memberikan pelayanan cepat, harga kompetitif, dan unit siap kerja.
      </p>
    </div>
  </section>

  {/* Booking */}
  <section className="py-16 px-6 bg-gray-100">
    <div className="max-w-3xl mx-auto">
      <h2 className="text-3xl font-bold text-center mb-8">Booking Cepat & Kalkulator Harga</h2>
      <form onSubmit={handleSubmit} className="space-y-6">
        <input name="nama" onChange={handleChange} required placeholder="Nama Lengkap" className="w-full p-3 border rounded-2xl" />
        <input name="telepon" onChange={handleChange} required placeholder="Nomor Telepon" className="w-full p-3 border rounded-2xl" />
        <input name="lokasi" onChange={handleChange} required placeholder="Lokasi Proyek" className="w-full p-3 border rounded-2xl" />
        <select name="unit" onChange={handleChange} required className="w-full p-3 border rounded-2xl">
          <option value="">Pilih Unit</option>
          {Object.keys(prices).map((u,i)=>(<option key={i}>{u}</option>))}
        </select>
        <input name="durasi" type="number" min="1" value={form.durasi} onChange={handleChange} required className="w-full p-3 border rounded-2xl" />

        {form.unit && (
          <div className="text-center text-xl font-bold">
            Total Estimasi: Rp {totalHarga.toLocaleString()}
          </div>
        )}

        <Button type="submit" className="w-full rounded-2xl">
          Kirim Booking ke WhatsApp
        </Button>
      </form>
    </div>
  </section>

  {/* Floating WA */}
  <a href={`https://wa.me/${phoneNumber}`} target="_blank" rel="noopener noreferrer" className="fixed bottom-6 right-6 bg-green-500 text-white p-4 rounded-full shadow-2xl">
    <MessageCircle />
  </a>

  <footer className="bg-black text-white py-6 text-center">
    <p>© {new Date().getFullYear()} Jaya Keluarga Mandiri</p>
    <p>Rental Excavator Jabodetabek | Telp: {displayPhone}</p>
  </footer>
</div>

); }
