<template>
  <table class="w-full">
    <thead>
      <tr>
        <th colspan="3">Factuur</th>
      </tr>
    </thead>
    <tbody> 
      <tr>
        <td colspan="2" class="px-4">Klantnummer: 123</td>
        <td class="font-semibold px-4">Factuurdatum</td>
      </tr>
      <tr>
        <td colspan="2" class="px-4">Jan Jansen</td>
        <td class="px-4">{{ new Date().getDate() + '-' + (new Date().getMonth() + 1) + '-' + new Date().getFullYear() }}</td>
      </tr>
      <tr>
        <td colspan="2" class="px-4">Dorpstraat 12</td>
        <td class="font-semibold px-4">Factuurnummer</td>
      </tr>
      <tr>
        <td colspan="2" class="px-4">Roermond</td>
        <td class="px-4">{{ new Date().getFullYear() }}3184</td>
      </tr>
      <tr>
        <td class="px-4 pt-6 font-semibold">Aantal</td>
        <td class="px-4 pt-6 font-semibold">Omschrijving</td>
        <td class="px-4 pt-6 font-semibold">Prijs</td>
      </tr>
      <tr>
        <td class="px-4">1</td>
        <td class="px-4">Macbook Pro {{ new Date().getFullYear() }}</td>
        <td class="px-4">&euro; 3.299</td>
      </tr>
      <tr>
        <td class="px-4">3</td>
        <td class="px-4">2.2kg PLA filament BLAUW</td>
        <td class="px-4">&euro; 25,50</td>
      </tr>
      <tr>
        <td class="px-4">2</td>
        <td class="px-4">Douwe Egberts Koffiebonen 1KG</td>
        <td class="px-4">&euro; 7,99</td>
      </tr>
      <tr>
        <td class="px-4 pt-2"></td>
        <td class="px-4 pt-2 text-right">Subtotaal: </td>
        <td class="px-4 pt-2">&euro; 3.391,48</td>
      </tr>
      <tr>
        <td class="px-4"></td>
        <td class="px-4 text-right">BTW (21%): </td>
        <td class="px-4">&euro; 712,21</td>
      </tr>
      <tr>
        <td class="px-4"></td>
        <td class="px-4 text-right">Totaal: </td>
        <td class="px-4">&euro; 4.103,69</td>
      </tr>
    </tbody>
  </table>
</template>
