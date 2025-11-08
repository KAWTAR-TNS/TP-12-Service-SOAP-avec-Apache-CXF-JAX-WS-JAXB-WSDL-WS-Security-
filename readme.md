# Structure WSDL - Tableau Récapitulatif

| Section WSDL | Balises Clés | Rôle et Fonction |
|--------------|--------------|------------------|
| `<types>` | `<xs:schema>`, `<xs:complexType name="person">` | Définit le dictionnaire de données (XSD). C'est ici que sont structurés les objets échangés (ex. : l'objet person avec age, id, name). |
| `<message>` | `<wsdl:part element="...">` | Définit les enveloppes logiques pour les données. Il fait le lien entre les opérations et les types XSD (ex. : le message FindPerson contient l'élément XSD FindPerson). |
| `<portType>` | `<wsdl:operation>`, `<wsdl:input>`, `<wsdl:output>` | Représente l'interface métier abstraite. Il définit les opérations du service (méthodes) sans référence à un protocole (ex. : les opérations FindPerson et SayHello). |
| `<binding>` | `<soap:binding>`, `<soap:operation>` | Décrit le protocole concret. Il mappe le portType au protocole SOAP sur HTTP et spécifie l'encodage (style="document"). |
| `<service>` | `<wsdl:port>`, `<soap:address location="...">` | Fournit le point d'accès physique (Endpoint). Il indique l'URL réelle où le service est déployé et accessible (ex. : http://localhost:8080/services/hello). |


## Exemple de WSDL Généré
<table align="center">
  <tr>
    <td align="center" style="border: 2px solid #007acc; padding: 10px; border-radius: 8px;">
      <img src="docs/1.png" alt="Structure WSDL" width="600"/>
      <br/>
      <em>Structure WSDL générée - Service SOAP CXF</em>
    </td>
  </tr>
</table>

## SoapUI pour importer l’URL du WSDL
<table align="center">
  <tr>
    <td align="center" style="border: 2px solid #007acc; padding: 10px; border-radius: 8px;">
      <img src="docs/2.png" alt="Structure WSDL" width="600"/>
      <br/>
      <em> SoapUI pour importer l’URL du WSDL</em>
    </td>
  </tr>
</table>

## Génération des Stubs Client avec wsdl2java (CXF)
<table align="center">
  <tr>
    <td align="center" style="border: 2px solid #007acc; padding: 10px; border-radius: 8px;">
      <img src="docs/3.png" alt="Structure WSDL" width="600"/>
      <br/>
      <em> Génération des Stubs Client avec wsdl2java (CXF)</em>
    </td>
  </tr>
</table>