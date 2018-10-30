---
title: Utilisation des options de la ligne de commande Setup
TOCTitle: Utilisation des options de la ligne de commande Setup
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205129(v=OCS.15)
ms:contentKeyID: 49298262
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation des options de la ligne de commande Setup

 

_**Dernière rubrique modifiée :** 2016-12-08_

La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande du programme d’installation, on utilise généralement l’Outil de personnalisation Office et le fichier Config.xml pour personnaliser l’installation du produit et ses fonctionnalités.

La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.

### Options de la ligne de commande du programme d’installation Office

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Options de ligne de commande du programme d’installation</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Exécute l’Outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [chemin]</p></td>
<td><p>Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</p></td>
</tr>
<tr class="odd">
<td><p>/config [chemin]</p></td>
<td><p>Spécifie le fichier Config.xml utilisé par le programme d’installation au cours de l’installation. Utilisez l’option /config pour spécifier le fichier Config.xml que vous avez personnalisé pour les installations de Lync 2013, par exemple : <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option /modify pour ajouter ou supprimer des fonctionnalités de Lync.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Lync.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Exécute le programme d’installation pour supprimer Lync de l’ordinateur de l’utilisateur.</p></td>
</tr>
</tbody>
</table>


Pour plus d’informations sur l’utilisation des options de ligne de commande du programme d’installation, voir [http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0x40c).

