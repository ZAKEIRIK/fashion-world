// Homepage for Jessica Louise inspired by Jogiel.com
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Play } from "lucide-react";
import Image from "next/image";
import Script from "next/script";

export default function HomePage() {
  return (
    <main className="min-h-screen w-full bg-black text-white font-sans">
      {/* Hero Section */}
      <section className="relative h-screen w-full overflow-hidden">
        <video
          autoPlay
          loop
          muted
          className="absolute inset-0 w-full h-full object-cover opacity-70"
        >
          <source src="/videos/hero.mp4" type="video/mp4" />
        </video>
        <div className="relative z-10 flex flex-col items-center justify-center h-full text-center px-4">
          <h1 className="text-5xl md:text-7xl font-bold tracking-wide uppercase drop-shadow-lg">
            Jessica Louise
          </h1>
          <p className="mt-4 text-lg md:text-xl max-w-xl">
            Punk Couture for the Fearless. Discover the New Collection.
          </p>
          <Button className="mt-6 text-black bg-white hover:bg-pink-500 hover:text-white transition-all">
            Shop Now
          </Button>
        </div>
      </section>

      {/* Collection Highlights */}
      <section className="py-20 px-6 grid grid-cols-1 md:grid-cols-3 gap-6 bg-white text-black">
        {[1, 2, 3].map((_, i) => (
          <Card key={i} className="rounded-2xl overflow-hidden shadow-xl">
            <CardContent className="p-0">
              <Image
                src={`/images/collection${i + 1}.jpg`}
                alt={`Collection ${i + 1}`}
                width={600}
                height={800}
                className="w-full h-auto object-cover"
              />
            </CardContent>
          </Card>
        ))}
      </section>

      {/* Lookbook Section */}
      <section className="bg-black text-white py-16 px-8 text-center">
        <h2 className="text-4xl font-bold uppercase mb-10">Lookbook</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {[1, 2, 3].map((_, i) => (
            <Image
              key={i}
              src={`/images/lookbook${i + 1}.jpg`}
              alt={`Lookbook ${i + 1}`}
              width={600}
              height={800}
              className="rounded-xl object-cover w-full"
            />
          ))}
        </div>
      </section>

      {/* Shop Preview Section with Shopify Buy Buttons */}
      <section className="bg-white text-black py-20 px-6">
        <h2 className="text-4xl font-bold uppercase text-center mb-10">Shop Featured</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {[1, 2, 3].map((_, i) => (
            <div
              key={i}
              className="w-full rounded-2xl overflow-hidden shadow-xl bg-white text-black p-4"
            >
              <div
                dangerouslySetInnerHTML={{
                  __html: `<iframe src="https://fashion-world.myshopify.com/embed/PRODUCT_HANDLE_${i + 1}" width="100%" height="600" frameborder="0"></iframe>`
                }}
              />
            </div>
          ))}
        </div>
      </section>

      {/* About Section */}
      <section className="bg-black text-white py-16 px-8 text-center">
        <h2 className="text-4xl font-bold uppercase mb-4">About Jessica</h2>
        <p className="max-w-3xl mx-auto text-lg">
          Jessica Louise is a Los Angeles-based fashion designer known for blending punk
          rock edge with glam couture. Her work has been featured in countless magazines,
          music videos, and runway shows.
        </p>
      </section>

      {/* Newsletter CTA */}
      <section className="bg-pink-600 text-white py-16 px-8 text-center">
        <h3 className="text-3xl font-semibold mb-4">Join Our Mailing List</h3>
        <p className="mb-6">Be the first to hear about new collections, events, and sales.</p>
        <form className="flex flex-col md:flex-row justify-center items-center gap-4">
          <input
            type="email"
            placeholder="Enter your email"
            className="px-4 py-2 rounded-full text-black"
          />
          <Button className="bg-black hover:bg-white hover:text-black transition-all">
            Subscribe
          </Button>
        </form>
      </section>

      {/* Footer */}
      <footer className="bg-black text-white text-center py-6 text-sm">
        © {new Date().getFullYear()} Jessica Louise. All rights reserved.
      </footer>
    </main>
  );
}
