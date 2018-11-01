---
title: Utilisation de Config.xml pour l’exécution des tâches d’installation
TOCTitle: Utilisation de Config.xml pour l’exécution des tâches d’installation
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204651(v=OCS.15)
ms:contentKeyID: 49296163
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de Config.xml pour l’exécution des tâches d’installation

 

_**Dernière rubrique modifiée :** 2016-12-08_

Bien que l’outil de personnalisation Office soit le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations suivantes ne peuvent être effectuées qu’avec le fichier Config.xml :

  - spécifier le chemin d’accès au point d’installation réseau ;

  - sélectionner les produits à installer ;

  - configurer la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels ;

  - spécifier les options d’installation telles que le nom de l’utilisateur ;

  - copier la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office ;

  - ajouter ou supprimer des langues de l’installation.

Nous vous recommandons d’utiliser le fichier Config.xml file pour configurer l’installation de Lync 2013 sans assistance.

Par défaut, le fichier Config.xml stocké dans le dossier de produit principal (par exemple, \\*produit*.WW) indique au programme d’installation d’installer ce produit. Par exemple, le fichier Config.xml dans le dossier suivant installe Lync 2013 :

  - \\\\server\\share\\Lync15\\Lync.WW \\Config.xml

Les éléments de Config.xml les plus couramment utilisés pour l’installation de Lync 2013 sont répertoriés dans le tableau suivant.

### Éléments de Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Élément</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées pendant l’installation. Utilisez les attributs suivants pour empêcher l’installation de Business Connectivity Services, qui comprend des composants partagés qui interfèrent avec Outlook 2010:</p>
<ul>
<li><p>Id=&quot;LOBiMain&quot;</p></li>
<li><p>State=&quot;Absent&quot;</p></li>
<li><p>Children=&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p>
<p></p></td>
<td><p>Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants :</p>
<ul>
<li><p>CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(par défaut)</p></li>
<li><p>AcceptEula=&quot;Yes&quot; | &quot;No&quot;(par défaut)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants :</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(par défaut) | &quot;Verbose&quot;</p></li>
<li><p>Template=”<em>nomfichier</em>.txt” (nom du fichier journal)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Setting</p></td>
<td><p>Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :</p>
<ul>
<li><p>Setting Id=&quot;<em>nom</em>&quot; (nom de la propriété de Windows Installer)</p></li>
<li><p>Value=&quot;<em>valeur</em>&quot; (valeur à attribuer à la propriété)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :</p>
<ul>
<li><p>Location=”<em>chemin d’accès</em>”</p></li>
</ul></td>
</tr>
</tbody>
</table>


L’exemple suivant montre un fichier Config.xml pour une installation sans assistance de Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Vous trouverez des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer les tâches d’installation et de maintenance d’Office à l’adresse [http://go.microsoft.com/fwlink/?linkid=267514\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267514%26clcid=0x40c).

## Pour personnaliser le fichier Config.xml

1.  Ouvrez le fichier Config.xml avec un éditeur de texte, tel que le Bloc-notes.

2.  Recherchez les lignes qui contiennent les éléments que vous voulez changer.

3.  Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Veillez à supprimer les délimiteurs de commentaires « \<\!-- » et « --\> ». Par exemple, utilisez la syntaxe suivante :
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Enregistrez le fichier Config.xml.

