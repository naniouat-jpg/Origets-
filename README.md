Voici la version corrigée, propre et fonctionnelle de ton code Next.js + Framer Motion + Shadcn UI.

Tu avais plusieurs erreurs :

❌ Problèmes détectés

Doublons énormes (le code répété 3 fois).

useState non importé.

Une ligne cassée : import { useRoute "next/router";

Une section <motion.div> non fermée.

Fin de composant manquante ())}, </div>, </Home>…).



---

✅ CODE FINAL CORRIGÉ ET PRÊT À L’USAGE

import { useState } from "react";
import { useRouter } from "next/router";
import { Input } from "@/components/ui/input";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Search } from "lucide-react";
import { motion } from "framer-motion";

export default function Home() {
  const router = useRouter();

  const [query, setQuery] = useState("");
  const [mode, setMode] = useState("patient");

  const features = [
    {
      title: "Sources Fiables",
      desc: "Basé sur PubMed, OMS, NICE, HAS, ClinicalTrials.gov et plus.",
    },
    {
      title: "Mode Patient / Médecin",
      desc: "Choisissez le mode d'explication adapté à votre niveau.",
    },
    {
      title: "Recherche Sémantique",
      desc: "Comprend le sens de votre question, pas seulement les mots.",
    },
  ];

  return (
    <div className="min-h-screen flex flex-col items-center justify-center bg-gray-50 p-6">

      {/* TITRE */}
      <motion.h1
        initial={{ opacity: 0, y: -20 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
        className="text-4xl md:text-6xl font-bold text-center mb-2 text-gray-800"
      >
        ORIGETS
      </motion.h1>

      {/* SOUS-TITRE */}
      <motion.h2
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.2, duration: 0.6 }}
        className="text-xl md:text-2xl font-medium text-center mb-6 text-gray-600"
      >
        Le moteur de santé nouvelle génération
      </motion.h2>

      {/* DESCRIPTION */}
      <motion.p
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.3, duration: 0.6 }}
        className="text-gray-600 text-center max-w-xl mb-10"
      >
        {mode === "patient"
          ? "Obtenez des informations médicales fiables expliquées simplement."
          : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}
      </motion.p>

      {/* MODE SELECTOR */}
      <div className="flex gap-4 mb-6">
        <Button
          variant={mode === "patient" ? "default" : "outline"}
          onClick={() => setMode("patient")}
          className="rounded-xl"
        >
          Patient
        </Button>

        <Button
          variant={mode === "medecin" ? "default" : "outline"}
          onClick={() => setMode("medecin")}
          className="rounded-xl"
        >
          Médecin
        </Button>
      </div>

      {/* SEARCH BOX */}
      <Card className="w-full max-w-2xl shadow-xl rounded-2xl">
        <CardContent className="p-6">
          <div className="flex gap-3">
            <Input
              type="text"
              placeholder={
                mode === "patient"
                  ? "Décrivez vos symptômes ou une question de santé..."
                  : "Recherchez une pathologie, un protocole, une recommandation..."
              }
              value={query}
              onChange={(e) => setQuery(e.target.value)}
              className="flex-1 p-4 text-lg rounded-xl"
            />

            <Button
              className="p-4 rounded-xl"
              size="lg"
              onClick={() => {
                if (!query.trim()) return;
                router.push(`/results?q=${encodeURIComponent(query)}&mode=${mode}`);
              }}
            >
              <Search />
            </Button>
          </div>
        </CardContent>
      </Card>

      {/* FEATURE GRID */}
      <div className="mt-16 grid grid-cols-1 md:grid-cols-3 gap-6 w-full max-w-4xl">
        {features.map((item, i) => (
          <motion.div
            key={i}
            initial={{ opacity: 0, y: 20 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ delay: 0.2 + i * 0.2 }}
            className="p-6 bg-white rounded-2xl shadow-md"
          >
            <h3 className="text-xl font-semibold mb-2">{item.title}</h3>
            <p className="text-gray-600">{item.desc}</p>
          </motion.div>
        ))}
      </div>

    </div>
  );
}


---

🎉 Résultat

Ton interface ORIGETS est maintenant :

✔️ propre
✔️ fonctionnelle
✔️ sans erreurs
✔️ mieux structurée


---

Si tu veux, je peux maintenant :

✨ Ajouter un logo animé ORIGETS
✨ Ajouter une animation d’étoile Origami
✨ Créer la page /results
✨ Faire un header fixe avec menu
✨ Mettre ton style visuel santé+ (couleurs, icônes, dégradés)

Dis-moi ce qu’on construit ensuite !
motion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient" ? "Obtenez des informations médicales fiables expliquées simplement." : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  [mode
      className
# Origets-
motion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient" ? "Obtenez des informations médicales fiables expliquées simplement." : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      classNamemotion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient" ? "Obtenez des informations médicales fiables expliquées simplement." : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      classNamemotion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient" ? "Obtenez des informations médicales fiables expliquées simplement." : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      classNameresults?q=...&mode= <motion.h2  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.2, duration: 0.6 }}  
    className="text-xl md:text-2xl font-medium text-center mb-6 text-gray-600"  
  >  
    Le moteur de santé nouvelle génération  
  </motion.h2>  

  <motion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient"  
      ? "Obtenez des informations médicales fiables expliquées simplement."  
      : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      className="rounded-xl"  
    >  
      Patient  
    </Button>  
    <Button  
      variant={mode === "medecin" ? "default" : "outline"}  
      onClick={() => setMode("medecin")}  
      className="rounded-xl"  
    >  
      Médecin  
    </Button>  
  </div>  
<motion.h2  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.2, duration: 0.6 }}  
    className="text-xl md:text-2xl font-medium text-center mb-6 text-gray-600"  
  >  
    Le moteur de santé nouvelle génération  
  </motion.h2>  

  <motion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient"  
      ? "Obtenez des informations médicales fiables expliquées simplement."  
      : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      className="rounded-xl"  
    >  
      Patient  
    </Button>  
    <Button  
      variant={mode === "medecin" ? "default" : "outline"}  
      onClick={() => setMode("medecin")}  
      className="rounded-xl"  
    >  
      Médecin  
    </Button>  
  </div>  
<motion.h2  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.2, duration: 0.6 }}  
    className="text-xl md:text-2xl font-medium text-center mb-6 text-gray-600"  
  >  
    Le moteur de santé nouvelle génération  
  </motion.h2>  

  <motion.p  
    initial={{ opacity: 0 }}  
    animate={{ opacity: 1 }}  
    transition={{ delay: 0.3, duration: 0.6 }}  
    className="text-gray-600 text-center max-w-xl mb-10"  
  >  
    {mode === "patient"  
      ? "Obtenez des informations médicales fiables expliquées simplement."  
      : "Consultez des sources scientifiques validées : guidelines, PubMed, essais cliniques."}  
  </motion.p>  

  <div className="flex gap-4 mb-6">  
    <Button  
      variant={mode === "patient" ? "default" : "outline"}  
      onClick={() => setMode("patient")}  
      className="rounded-xl"  
    >  
      Patient  
    </Button>  
    <Button  
      variant={mode === "medecin" ? "default" : "outline"}  
      onClick={() => setMode("medecin")}  
      className="rounded-xl"  
    >  
      Médecin  
    </Button>  
  </d