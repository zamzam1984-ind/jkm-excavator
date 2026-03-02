import React, { useEffect } from "react";

export default function HomePage() {
  useEffect(() => {
    document.title =
      "Rental Excavator Jabodetabek | Jaya Keluarga Mandiri";

    const meta = document.createElement("meta");
    meta.name = "description";
    meta.content =
      "Jaya Keluarga Mandiri melayani rental excavator Jakarta, Bekasi, Tangerang, Depok, dan Bogor. Harga kompetitif dan unit siap kerja.";
    document.head.appendChild(meta);

    const script = document.createElement("script");
    script.type = "application/ld+json";
    script.innerHTML = JSON.stringify({
      "@context": "https://schema.org",
      "@type": "LocalBusiness",
      name: "Jaya Keluarga Mandiri",
      telephone: "+6281229637820",
      areaServed: "Jabodetabek",
      serviceType: "Rental Excavator",
    });
    document.head.appendChild(script);
  }, []);

  return (
    <div className="min-h-screen bg-gray-50 text-gray-800">
      {/* NAVBAR */}
      <nav className="bg-white shadow-md py-4 px-6 flex justify-between items-center">
        <div className="font-bold text-lg">
          Jaya Keluarga Mandiri
        </div>
        <a
          href="https://wa.me/6281229637820"
          target="_blank"
          rel="noopener noreferrer"
          className="bg-yellow-500 text-black px-4 py-2 rounded-xl font-semibold"
        >
          WhatsApp
        </a>
      </nav>

      {/* HERO */}
      <section className="bg-yellow-500 text-black py-20 px-6 text-center">
        <h1 className="text-4xl md:text-6xl font-bold mb-6">
          Rental Excavator Jabodetabek
        </h1>
        <p className="text-lg md:text-xl mb-8 max-w-2xl mx-auto">
          Melayani sewa excavator untuk proyek konstruksi, cut & fill,
          pembongkaran bangunan, dan perataan tanah di Jakarta, Bekasi,
          Tangerang, Depok, dan Bogor.
        </p>
        <a
          href="https://wa.me/6281229637820"
          target="_blank"
          rel="noopener noreferrer"
          className="inline-block bg-black text-white text-lg px-8 py-4 rounded-2xl shadow-xl"
        >
          Hubungi via WhatsApp
        </a>
      </section>

      {/* LAYANAN */}
      <section className="py-16 px-6 max-w-6xl mx-auto">
        <h2 className="text-3xl font-bold text-center mb-12">
          Layanan Kami
        </h2>
        <div className="grid md:grid-cols-3 gap-6">
          {[
            "Proyek Konstruksi",
            "Cut & Fill",
            "Pembongkaran Bangunan",
          ].map((item, index) => (
            <div
              key={index}
              className="bg-white rounded-2xl shadow-lg p-6 text-center"
            >
              <div className="text-4xl mb-4">🚜</div>
              <h3 className="text-xl font-semibold mb-2">{item}</h3>
              <p>
                Operator berpengalaman dan unit terawat siap mendukung proyek
                Anda.
              </p>
            </div>
          ))}
        </div>
      </section>

      {/* AREA */}
      <section className="bg-white py-16 px-6">
        <h2 className="text-3xl font-bold text-center mb-10">
          Area Layanan
        </h2>
        <div className="grid md:grid-cols-5 gap-4 max-w-6xl mx-auto text-center">
          {["Jakarta", "Bekasi", "Tangerang", "Depok", "Bogor"].map(
            (city, index) => (
              <div
                key={index}
                className="bg-gray-100 p-6 rounded-2xl shadow"
              >
                <div className="text-2xl mb-2">📍</div>
                <p className="font-semibold">{city}</p>
              </div>
            )
          )}
        </div>
      </section>

      {/* HARGA */}
      <section className="py-16 px-6 max-w-4xl mx-auto text-center">
        <h2 className="text-3xl font-bold mb-8">Harga Mulai</h2>
        <div className="bg-white rounded-2xl shadow-xl p-10">
          <p className="text-4xl font-bold mb-4">Rp 3.000.000 / Hari</p>
          <p className="mb-6">
            Harga tergantung tipe unit, durasi sewa, dan lokasi proyek.
          </p>
          <a
            href="https://wa.me/6281229637820"
            target="_blank"
            rel="noopener noreferrer"
            className="inline-block bg-yellow-500 text-black px-6 py-4 rounded-2xl shadow-lg"
          >
            Cek Ketersediaan Unit
          </a>
        </div>
      </section>

      {/* CTA */}
      <section className="bg-yellow-500 py-16 px-6 text-center">
        <h2 className="text-3xl font-bold mb-6">
          Butuh Excavator Sekarang?
        </h2>
        <p className="mb-8">
          Hubungi kami sekarang dan dapatkan penawaran terbaik untuk proyek
          Anda.
        </p>
        <a
          href="https://wa.me/6281229637820"
          target="_blank"
          rel="noopener noreferrer"
          className="inline-block bg-black text-white text-lg px-8 py-4 rounded-2xl shadow-xl"
        >
          Chat Sekarang
        </a>
      </section>

      {/* FOOTER */}
      <footer className="bg-gray-900 text-white py-10 px-6 text-center">
        <h3 className="text-xl font-bold mb-4">Jaya Keluarga Mandiri</h3>
        <p className="mb-2">Rental Excavator Jabodetabek</p>
        <p className="mb-4">📞 +62 812-2963-7820</p>
        <p className="text-sm text-gray-400">
          © {new Date().getFullYear()} Jaya Keluarga Mandiri. All rights
          reserved.
        </p>
      </footer>
    </div>
  );
}
