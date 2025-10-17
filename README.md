import React, { useState } from 'react';
import { ShoppingCart, Heart, Instagram, Twitter, Facebook, Mail, Phone, MapPin, Leaf, Users, Zap, Award } from 'lucide-react';

const App = () => {
  const [cartItems, setCartItems] = useState(0);

  const products = [
    {
      id: 1,
      name: 'Camisetas',
      price: 25,
      description: 'Diseño exclusivo con logo característico. Confeccionadas en algodón premium 100% para máxima comodidad, con estampado duradero y diseño urbano distintivo.',
      features: ['Algodón premium 100%', 'Estampado duradero', 'Diseño urbano distintivo'],
      image: 'https://placehold.co/400x500/f0f0f0/333333?text=Camiseta+IYS+Modelo',
      stock: '500+ unidades/día'
    },
    {
      id: 2,
      name: 'Pantalones',
      price: 55,
      description: 'Jeans de corte holgado con detalles exclusivos. Confeccionados en Denim de alta resistencia. Incluyen logo bordado en el bolsillo trasero y cadena decorativa incluida.',
      features: ['Denim de alta resistencia', 'Logo bordado en bolsillo', 'Cadena decorativa incluida'],
      image: 'https://placehold.co/400x500/e0e0e0/333333?text=Pantalones+IYS+Modelo',
      stock: '300+ unidades/mes'
    },
    {
      id: 3,
      name: 'Cinturones',
      price: 35,
      description: 'Cinturón de cuero genuino premium con hebilla metálica exclusiva. Diseño elegante y duradero que complementa cualquier outfit. Cuenta con un acabado resistente al desgaste.',
      features: ['Cuero genuino premium', 'Hebilla metálica exclusiva', 'Acabado resistente al desgaste'],
      image: 'https://placehold.co/400x500/d0d0d0/333333?text=Cinturón+IYS+Modelo',
      stock: '200+ unidades/mes'
    }
  ];

  const communityImages = [
    'https://placehold.co/400x400/2a2a2a/ffffff?text=Cliente+1+IYS',
    'https://placehold.co/400x400/3a3a3a/ffffff?text=Cliente+2+IYS',
    'https://placehold.co/400x400/4a4a4a/ffffff?text=Cliente+3+IYS'
  ];

  const addToCart = () => {
    setCartItems(cartItems + 1);
  };

  return (
    <div className="min-h-screen bg-black text-white">
      {/* Header */}
      <header className="sticky top-0 z-50 bg-black border-b border-gray-800">
        <div className="container mx-auto px-4 py-4 flex justify-between items-center">
          <div className="flex items-center space-x-3">
            <img 
              src="https://placehold.co/50x50/ffffff/000000?text=IYS" 
              alt="Improve Your Style Logo"
              className="w-12 h-12"
            />
            <h1 className="text-2xl font-bold hidden md:block">Improve Your Style</h1>
          </div>
          
          <nav className="hidden md:flex space-x-8">
            <a href="#productos" className="hover:text-gray-300 transition-colors">Productos</a>
            <a href="#sobre-nosotros" className="hover:text-gray-300 transition-colors">Sobre Nosotros</a>
            <a href="#sostenibilidad" className="hover:text-gray-300 transition-colors">Sostenibilidad</a>
            <a href="#comunidad" className="hover:text-gray-300 transition-colors">Comunidad</a>
          </nav>

          <div className="flex items-center space-x-4">
            <button className="p-2 hover:text-gray-300 transition-colors">
              <Heart size={24} />
            </button>
            <button className="p-2 hover:text-gray-300 transition-colors relative">
              <ShoppingCart size={24} />
              {cartItems > 0 && (
                <span className="absolute -top-2 -right-2 bg-red-600 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">
                  {cartItems}
                </span>
              )}
            </button>
          </div>
        </div>
      </header>

      {/* Hero Section */}
      <section className="relative h-screen flex items-center justify-center bg-gradient-to-br from-gray-900 to-black">
        <div className="absolute inset-0 bg-black opacity-50"></div>
        <div className="relative z-10 text-center px-4 max-w-4xl">
          <h2 className="text-5xl md:text-7xl font-bold mb-6 tracking-tight">
            EXPRESA TU
            <span className="block text-red-600">IDENTIDAD</span>
          </h2>
          <p className="text-xl md:text-2xl text-gray-300 mb-8">
            Ropa urbana de calidad con diseño distintivo que permite expresar tu personalidad
          </p>
          <button 
            onClick={() => document.getElementById('productos').scrollIntoView({ behavior: 'smooth' })}
            className="bg-red-600 hover:bg-red-700 text-white px-8 py-4 rounded-full text-lg font-semibold transition-colors transform hover:scale-105"
          >
            Descubre Nuestra Colección
          </button>
        </div>
      </section>

      {/* Brand Values */}
      <section className="py-16 bg-gray-900">
        <div className="container mx-auto px-4">
          <div className="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
            <div className="flex flex-col items-center">
              <Award className="w-12 h-12 text-red-600 mb-4" />
              <h3 className="text-xl font-bold mb-2">Calidad</h3>
              <p className="text-gray-400">Materiales premium y acabados impecables</p>
            </div>
            <div className="flex flex-col items-center">
              <Zap className="w-12 h-12 text-red-600 mb-4" />
              <h3 className="text-xl font-bold mb-2">Innovación</h3>
              <p className="text-gray-400">Diseños que marcan tendencia</p>
            </div>
            <div className="flex flex-col items-center">
              <Leaf className="w-12 h-12 text-red-600 mb-4" />
              <h3 className="text-xl font-bold mb-2">Sostenibilidad</h3>
              <p className="text-gray-400">Procesos responsables con el medio ambiente</p>
            </div>
            <div className="flex flex-col items-center">
              <Users className="w-12 h-12 text-red-600 mb-4" />
              <h3 className="text-xl font-bold mb-2">Comunidad</h3>
              <p className="text-gray-400">Conectamos con nuestros clientes</p>
            </div>
          </div>
        </div>
      </section>

      {/* Products Section */}
      <section id="productos" className="py-20 bg-black">
        <div className="container mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16">Nuestra Colección</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-12">
            {products.map((product) => (
              <div key={product.id} className="bg-gray-900 rounded-xl overflow-hidden hover:transform hover:scale-105 transition-all duration-300">
                <div className="relative">
                  <img 
                    src={product.image} 
                    alt={product.name}
                    className="w-full h-96 object-cover"
                  />
                  <div className="absolute top-4 right-4 bg-red-600 text-white px-3 py-1 rounded-full text-sm font-semibold">
                    €{product.price}
                  </div>
                </div>
                <div className="p-6">
                  <h3 className="text-2xl font-bold mb-3">{product.name}</h3>
                  <p className="text-gray-300 mb-4">{product.description}</p>
                  
                  <div className="mb-4">
                    <h4 className="font-semibold mb-2">Características:</h4>
                    <ul className="space-y-1">
                      {product.features.map((feature, index) => (
                        <li key={index} className="text-gray-400 flex items-center">
                          <span className="w-2 h-2 bg-red-600 rounded-full mr-3"></span>
                          {feature}
                        </li>
                      ))}
                    </ul>
                  </div>
                  
                  <div className="flex justify-between items-center">
                    <span className="text-sm text-gray-500">{product.stock}</span>
                    <button 
                      onClick={addToCart}
                      className="bg-red-600 hover:bg-red-700 text-white px-6 py-2 rounded-full font-semibold transition-colors"
                    >
                      Añadir al Carrito
                    </button>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Sustainability Section */}
      <section id="sostenibilidad" className="py-20 bg-gradient-to-r from-green-900 to-emerald-900">
        <div className="container mx-auto px-4 text-center">
          <Leaf className="w-16 h-16 text-green-400 mx-auto mb-6" />
          <h2 className="text-4xl font-bold mb-6">Compromiso con la Sostenibilidad</h2>
          <p className="text-xl text-gray-200 max-w-3xl mx-auto mb-8">
            En Improve Your Style, creemos en la moda responsable. Nuestros procesos están diseñados 
            para minimizar el impacto ambiental, y estamos comprometidos con el lanzamiento de nuestra 
            línea de productos sostenibles para 2026.
          </p>
          <div className="bg-black bg-opacity-30 rounded-xl p-8 max-w-2xl mx-auto">
            <h3 className="text-2xl font-bold mb-4">Nuestros Compromisos:</h3>
            <ul className="text-left space-y-2">
              <li className="flex items-center">
                <span className="w-2 h-2 bg-green-400 rounded-full mr-3"></span>
                Materiales sostenibles y reciclados
              </li>
              <li className="flex items-center">
                <span className="w-2 h-2 bg-green-400 rounded-full mr-3"></span>
                Procesos de producción responsables
              </li>
              <li className="flex items-center">
                <span className="w-2 h-2 bg-green-400 rounded-full mr-3"></span>
                Embalaje ecológico y biodegradable
              </li>
              <li className="flex items-center">
                <span className="w-2 h-2 bg-green-400 rounded-full mr-3"></span>
                Línea sostenible lanzamiento 2026
              </li>
            </ul>
          </div>
        </div>
      </section>

      {/* Community Section */}
      <section id="comunidad" className="py-20 bg-gray-900">
        <div className="container mx-auto px-4">
          <h2 className="text-4xl font-bold text-center mb-16">Nuestra Comunidad</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {communityImages.map((img, index) => (
              <div key={index} className="bg-black rounded-xl overflow-hidden">
                <img 
                  src={img} 
                  alt={`Comunidad ${index + 1}`}
                  className="w-full h-64 object-cover"
                />
                <div className="p-4">
                  <p className="text-gray-300">"Estilo urbano auténtico con calidad premium"</p>
                  <p className="text-gray-500 mt-2">- Cliente IYS</p>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* About Us */}
      <section id="sobre-nosotros" className="py-20 bg-black">
        <div className="container mx-auto px-4">
          <div className="max-w-4xl mx-auto text-center">
            <h2 className="text-4xl font-bold mb-8">Sobre Improve Your Style</h2>
            <p className="text-xl text-gray-300 mb-6">
              Somos una marca emergente de moda urbana que combina diseño exclusivo con calidad superior. 
              Nuestros productos están pensados para quienes buscan expresar su identidad a través de 
              prendas únicas y duraderas.
            </p>
            
            {/* Logo Identity Section */}
            <div className="mt-12 bg-gray-900 rounded-xl p-8">
              <h3 className="text-2xl font-bold mb-6">Nuestra Identidad Visual</h3>
              <div className="grid grid-cols-2 md:grid-cols-4 gap-6">
                <div className="text-center">
                  <img 
                    src="https://placehold.co/120x120/ffffff/000000?text=LOGO+1" 
                    alt="Logotipo Principal"
                    className="w-24 h-24 mx-auto mb-2 rounded-lg"
                  />
                  <p className="text-sm text-gray-400">Principal</p>
                </div>
                <div className="text-center">
                  <img 
                    src="https://placehold.co/100x100/333333/ffffff?text=IYS" 
                    alt="Logotipo Secundario"
                    className="w-20 h-20 mx-auto mb-2 rounded-lg"
                  />
                  <p className="text-sm text-gray-400">Secundario</p>
                </div>
                <div className="text-center">
                  <img 
                    src="https://placehold.co/80x80/666666/ffffff?text=I" 
                    alt="Logotipo Submarca"
                    className="w-16 h-16 mx-auto mb-2 rounded-lg"
                  />
                  <p className="text-sm text-gray-400">Submarca</p>
                </div>
                <div className="text-center">
                  <img 
                    src="https://placehold.co/100x40/000000/ffffff?text=IYS" 
                    alt="Logo Simplificado"
                    className="w-24 h-10 mx-auto mb-2"
                  />
                  <p className="text-sm text-gray-400">Simplificado</p>
                </div>
              </div>
            </div>
            
            <div className="grid grid-cols-1 md:grid-cols-2 gap-8 mt-12">
              <div className="text-left">
                <h3 className="text-2xl font-bold mb-4 text-red-600">Misión</h3>
                <p className="text-gray-300">
                  Ofrecer ropa urbana de calidad con diseño distintivo que permita a nuestros clientes 
                  expresar su personalidad.
                </p>
              </div>
              <div className="text-left">
                <h3 className="text-2xl font-bold mb-4 text-red-600">Visión</h3>
                <p className="text-gray-300">
                  Convertirnos en referente del mercado de moda urbana, reconocidos por nuestra 
                  innovación y calidad.
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 border-t border-gray-800 py-12">
        <div className="container mx-auto px-4">
          <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div>
              <div className="flex items-center space-x-3 mb-4">
                <img 
                  src="https://placehold.co/50x50/ffffff/000000?text=IYS" 
                  alt="Improve Your Style Logo"
                  className="w-12 h-12"
                />
                <h3 className="text-xl font-bold">Improve Your Style</h3>
              </div>
              <p className="text-gray-400">
                Ropa urbana de calidad con diseño distintivo que permite expresar tu personalidad.
              </p>
            </div>
            
            <div>
              <h4 className="text-lg font-bold mb-4">Contacto</h4>
              <div className="space-y-2 text-gray-400">
                <div className="flex items-center">
                  <Mail className="w-4 h-4 mr-2" />
                  invest@improveyourstyle.com
                </div>
                <div className="flex items-center">
                  <Phone className="w-4 h-4 mr-2" />
                  +34 900 123 456
                </div>
                <div className="flex items-center">
                  <MapPin className="w-4 h-4 mr-2" />
                  Madrid, España
                </div>
              </div>
            </div>
            
            <div>
              <h4 className="text-lg font-bold mb-4">Enlaces</h4>
              <div className="space-y-2">
                <a href="#productos" className="block text-gray-400 hover:text-white transition-colors">Productos</a>
                <a href="#sobre-nosotros" className="block text-gray-400 hover:text-white transition-colors">Sobre Nosotros</a>
                <a href="#sostenibilidad" className="block text-gray-400 hover:text-white transition-colors">Sostenibilidad</a>
                <a href="#comunidad" className="block text-gray-400 hover:text-white transition-colors">Comunidad</a>
              </div>
            </div>
            
            <div>
              <h4 className="text-lg font-bold mb-4">Síguenos</h4>
              <div className="flex space-x-4">
                <a href="#" className="text-gray-400 hover:text-white transition-colors">
                  <Instagram size={24} />
                </a>
                <a href="#" className="text-gray-400 hover:text-white transition-colors">
                  <Twitter size={24} />
                </a>
                <a href="#" className="text-gray-400 hover:text-white transition-colors">
                  <Facebook size={24} />
                </a>
              </div>
            </div>
          </div>
          
          <div className="border-t border-gray-800 mt-12 pt-8 text-center text-gray-500">
            <p>&copy; 2025 Improve Your Style. Todos los derechos reservados.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default App;
