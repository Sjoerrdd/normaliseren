<template>
  <div class="bg-gray-100 h-full min-h-screen">
    <div class="max-w-2xl mx-auto">

      <div class="pb-12">

        <div class="mb-8 pt-12">
          <h1 class="font-serif text-3xl text-gray-900">Wat is normaliseren?</h1>
          <p class="text-gray-800">Normaliseren is een techniek bij het ontwerpen van een database met als doel het spaarzaam omgaan met data en het voorkomen <abbr class="underline cursor-pointer" title="dezelfde data meervoudig vastleggen waardoor potentiéle fouten ontstaan">redundantie</abbr>. Bij het normaliseren dient men zich er bewust van te zijn dat er geen informatie verloren gaat</p>
        </div>

        <div class="mb-8">
          <h1 class="font-serif text-3xl text-gray-900">Normaalvormen</h1>
          <p class="mb-3 text-gray-800">Er bestaan meerdere normaalvormen, waarbij 1NF de eenvoudigste variant is en 5NF de meest complexe vorm. Wanneer er aan geen eisen voldaan wordt, spreekt men van een 0e normaalvorm. </p>
          <p class="mb-2 text-gray-800">De volgende normaalvormen bestaan:</p>

          <ul class="list-disc ml-6 text-gray-800">
            <li>0e normaalvorm (0NF)</li>
            <li>1e normaalvorm (1NF)</li>
            <li>2e normaalvorm (2NF)</li>
            <li>3e normaalvorm (3NF)</li>
            <li>Boyce-Codd-Normaalvorm (BCNF)</li>
            <li>4e normaalvorm (4NF)</li>
            <li>5e normaalvorm (5NF)</li>
          </ul>

          <p class="text-gray-800">In deze tutorial normaliseren we van de 0<sup>e</sup> normaalvorm tot en met de 3<sup>e</sup> normaalvorm.</p>
        </div>


        <div class="mb-8">
          <h1 class="font-serif text-3xl text-gray-900">Soorten gegevens</h1>
          <p class="mb-2 text-gray-800">Tijdens normaliseren kunnen we onderscheid maken uit 4 verschillende soorten gegevens:</p>

          <ul class="list-disc ml-6 text-gray-800">
            <li>Constante gegevens: Deze gegevens kunnen worden vervangen door een sjabloon.</li>
            <li>Vaste gegevens: Deze gegevens zijn uniek op ieder record, maar er mogen wel identieke kopieën zijn</li>
            <li>Proces gegevens: Deze gegevens worden gegenereerd met andere gegevens, zoals "totaalbedrag"</li>
            <li>Repeterende gegevens: Deze gegevens kunnen vaker voorkomen op één record, zoals factuurregels.</li>
          </ul>
        </div>

        <div class="mb-8">
          <h1 class="font-serif text-3xl text-gray-900">Opdracht</h1>
          <p class="mb-2">Normaliseer onderstaand factuur</p>

          <Card>
            <Invoice />
          </Card>
        </div>

        <div class="mb-12">
          <h1 class="font-serif text-3xl text-gray-900">0<sup>e</sup> normaalvorm</h1>

          <div class="mb-4">
            <h2 class="font-serif text-lg">Stap 1: </h2>
            <div class="mb-2">
              <p class="font-semibold">Neem alle constante gegevens.</p>
              <p class="text-gray-800">Labels: "Factuur", "Factuurdatum", "Factuurnummer", "Aantal", "Prijs", "Omschrijving", "Subtotaal", "BTW (21%)", "Totaal"</p>
            </div>
            <div class="mb-2">
              <p class="font-semibold">Neem alle proces gegevens.</p>
              <p class="text-gray-800">Subtotaal, BTW-bedrag, Totaal</p>
            </div>
            <div class="mb-2">
              <p class="font-semibold">Neem alle vaste gegevens.</p>
              <p class="text-gray-800">Klantnummer, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Factuurnummer, BTW Percentage</p>
            </div>
            <div class="mb-2">
              <p class="font-semibold">Neem alle repeterende gegevens.</p>
              <p class="text-gray-800">Artikelnummer, Aantal, Omschrijving, Prijs</p>
            </div>

            <h2 class="font-serif text-lg">Stap 2: </h2>
            <div class="mb-2">
              <p class="font-semibold">Verwijder alle constante- en procesgegevens</p>
              <p class="text-gray-800">Zet de vaste gegevens voorop, gevolgd door de repeterende groep en bepaal de <abbr title="De sleutel is een uniek gegeven, zoals een factuurnummer, klantnummer, BSN-nummer of studentnummer." class="cursor-pointer">sleutel</abbr></p>
              <Card>
                <p class="font-mono">
                  0NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage, RG(Artikelnummer, Aantal, Omschrijving, Prijs))
                </p>
              </Card>
            </div>
          </div>
        </div>

        <div class="mb-12">
          <h1 class="font-serif text-3xl text-gray-900">1<sup>e</sup> normaalvorm</h1>
          <p class="text-gray-800">De eerste normaalvorm maak je door de repeterende groep apart te vermelden op een tweede regel, en hier de sleutel van de eerste regel aan toe te voegen. Bepaal ook een nieuwe sleutel</p>

          <p class="font-mono mt-2 mb-2">0NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage, RG(Artikelnummer, Aantal, Omschrijving, Prijs))</p>

          <p class="text-gray-800">wordt</p>

          <Card>
            <p class="font-mono">
              1NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage) <br>
              (<span class="border-b-2 border-green-500">Factuurnummer</span>, <span class="border-b-2 border-blue-500">Artikelnummer</span> Aantal, Omschrijving, Prijs)
            </p>
          </Card>
        </div>


        <div class="mb-12">
          <h1 class="font-serif text-3xl text-gray-900">2<sup>e</sup> normaalvorm</h1>
          <p class="text-gray-800">Bij de tweede normaalvorm zijn we op zoek naar gegevens die <u>niet</u> tot de sleutel behoren en van slechts een gedeelte van de sleutel afhankelijk zijn. Neem deze gegevens apart en voeg het gedeelte van de sleutel waar zij van afhankelijk zijn, als sleutel toe.</p>

          <Card>
            <p class="font-mono">
              1NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, <span class="border-b-2 border-green-500">Factuurnummer</span>, Aantal, Omschrijving, Prijs)
            </p>
          </Card>

          <p class="text-gray-800">wordt</p>

          <Card>
            <p class="font-mono">
              2NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, <span class="border-b-2 border-green-500">Factuurnummer</span>) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, Aantal, Omschrijving, Prijs)
            </p>
          </Card>
        </div>

        <div class="mb-8">
          <h1 class="font-serif text-3xl text-gray-900">3<sup>e</sup> normaalvorm</h1>
          <p class="text-gray-800">Bij de derde normaalvorm zijn we op zoek naar <u>niet-sleutelgegevens</u>, die allen afhankelijk zijn van andere <u>niet-sleutelgegevens</u>. Als die er zijn, laten we het gegeven waar zij afhankelijk van zijn staan, nemen de andere gegevens apart en voegen het gegeven waar zij van afhankelijk zijn als sleutel toe.</p>

          <Card>
            <p class="font-mono">
              2NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum, Klantnummer, BTW Percentage) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, <span class="border-b-2 border-green-500">Factuurnummer</span>) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, Aantal, Omschrijving, Prijs)
            </p>
          </Card>

          <p class="text-gray-800">wordt</p>

          <Card>
            <p class="font-mono">
              3NV(<span class="border-b-2 border-green-500">Factuurnummer</span>, <span class="border-b-2 border-red-500">Klantnummer</span>, BTW Percentage) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, <span class="border-b-2 border-green-500">Factuurnummer</span>) <br>
              (<span class="border-b-2 border-blue-500">Artikelnummer</span>, Aantal, Omschrijving, Prijs) <br>
              (<span class="border-b-2 border-red-500">Klantnummer</span>, Voornaam, Achternaam, Adres, Huisnummer, Woonplaats, Factuurdatum)
            </p>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Invoice from './components/Invoice'
import Card from './components/Card'

export default {
  components: { Invoice, Card }
}
</script>
