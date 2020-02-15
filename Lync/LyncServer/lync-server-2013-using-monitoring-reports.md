---
title: 'Lync Server 2013 : utilisation des rapports de surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37cd0f96ea0dd8e3fa63a851c3c93caf5988c7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Utilisation des rapports de surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Lync Server 2013 inclut un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE.

Pour pouvoir utiliser ces rapports, vous devez installer les rapports de surveillance sur un ordinateur qui exécute une instance de SQL Server.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Le tableau de bord de surveillance de Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   offre aux administrateurs une vue d’ensemble rapide de l’État et de l’utilisation du système.

  - [Les rapports d’utilisation du système dans Lync Server 2013](lync-server-2013-system-usage-reports.md)   fournissent des informations sur l’utilisation du système en fonction des données CDR recueillies par Lync Server.

  - [Call diagnostic Reports (Per User) dans Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   fournit des informations spécifiques à chaque utilisateur concernant les sessions de conférence et les sessions P2P ayant échoué.

  - [Call diagnostic reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   fournit des informations de synthèse et des données de diagnostic pour les sessions d’égal à égal et de conférence ayant échoué.

  - [Media Quality diagnostic reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fournit des informations sur la qualité des appels, ainsi que des informations de diagnostic et de résolution des problèmes pour les appels ayant échoué.

</div>

<div>

## <a name="locating-records"></a>Recherche d’enregistrements

Les rapports de surveillance affichent uniquement une quantité limitée d’enregistrements à l’écran. La quantité réelle d’enregistrements affichés sur un écran dépend du rapport. Pour visualiser les enregistrements qui ne sont pas affichés actuellement à l’écran, vous pouvez utiliser les contrôles standard « Précédent » et « Suivant » (qui se trouvent dans la barre d’outils de chaque rapport) qui vous permettent de parcourir les données. Vous pouvez également accéder rapidement à la première ou dernière page du jeu de données.

Outre ces contrôles, vous pouvez accéder à une page quelconque du jeu de données en tapant simplement son numéro dans la zone **Page actuelle**, puis en appuyant sur Entrée.

Chaque rapport offre également une possibilité limitée de rechercher des enregistrements. Pour rechercher des enregistrements sur la base d’une valeur donnée, tapez cette valeur dans la zone **Rechercher**, puis cliquez sur **Rechercher**. Le rapport commence à explorer les données et s’arrête sur la première instance de la valeur que vous avez entrée dans la zone **Rechercher**. Pour trouver l’enregistrement suivant qui répond aux critères de recherche, cliquez sur **Suivant**.

Comme mentionné plus haut, les rapports de surveillance procurent uniquement des fonctionnalités de recherche de base. Par exemple, vous ne pouvez pas spécifier le champ dans lequel rechercher la valeur. Le mécanisme de recherche recherche des valeurs correspondantes dans chaque champ de chaque enregistrement. Vous ne pouvez pas utiliser de caractères génériques dans vos recherches et toutes les recherches tentent de trouver des valeurs partielles. Cela signifie que si vous recherchez 111, la recherche renvoie la valeur 111, ainsi que les valeurs 11100, 811, 3112, 611A5B et tout autre champ qui comprend la valeur 111 n’importe où.

Chaque rapport est configuré de façon à afficher un ensemble d’enregistrements par défaut. Par exemple, par défaut le rapport Enregistrement d’utilisateur montre les activités d’enregistrement des utilisateurs pour la semaine passée. Dans certains cas, il se peut que le rapport soit vide, ce qui signifie que aucun enregistrement utilisateur n’a eu lieu durant la semaine passée. Si le message « Aucun résultat ne correspond aux filtres du rapport » s’affiche, essayez de modifier les valeurs de filtre (par exemple, sélectionnez le moi dernier plutôt que la semaine dernière comme période) et réexécutez la requête. Pour plus d’informations, voir la section « Filtrage des données » plus loin dans cette rubrique.

</div>

<div>

## <a name="filtering-data"></a>Filtrage des données

Il se peut parfois que vous souhaitiez examiner uniquement un sous-ensemble d’enregistrements, par exemple les sessions d’égal à égal plutôt que les sessions de conférence ET d’égal à égal. De même, il se peut que vous deviez réduire le nombre d’enregistrements renvoyés. Par défaut, un rapport ne peut afficher que les 1000 premiers enregistrements d’un jeu de données. Pour faire face à ces cas de figure, la plupart des rapports proposent plusieurs options de filtrage. Par exemple, si vous souhaitez afficher uniquement les enregistrements compris entre le 1er janvier 2011 et le 15 janvier 2011, vous pouvez entrer la date du 1er janvier 2011 dans la zone **De** et la date du 15 janvier 2011 dans la zone **À**. Si vous cliquez ensuite sur **Afficher le rapport**, les données renvoyées se limitent aux activités ayant eu lieu entre le 1er et le 15 janvier 2011.

Les filtres à votre disposition dépendent du rapport que vous visualisez. Pour plus d’informations sur un rapport spécifique, voir la rubrique d’aide relative à ce rapport.

</div>

<div>

## <a name="exporting-data"></a>Exportation de données

Les rapports de surveillance fournissent au moins deux manières différentes d’exporter les données incluses dans un rapport. Vous pouvez utiliser l’option **Exporter** de la barre d’outils affichée en haut de chaque rapport. Pour utiliser cette option, sélectionnez le format d’exportation souhaité dans la liste déroulante **Sélectionner un format**. Les formats suivants sont disponibles :

  - fichier XML avec données de rapport ;

  - fichier CSV (valeurs séparées par des virgules) ;

  - fichier Acrobat (PDF) ;

  - fichier MHTML (archive web) ;

  - Excel

  - fichier TIFF ;

  - Word

Après avoir sélectionné un format, cliquez sur **Exporter**. Lorsque la boîte de dialogue **Téléchargement de fichier** s’affiche, cliquez sur **Enregistrer**. Dans la boîte de dialogue **Enregistrer sous**, sélectionnez un dossier de destination, entrez un nom de fichier, puis cliquez sur **Enregistrer**.

Si Microsoft OneNote est installé, vous pouvez également copier les données de rapport dans OneNote. Pour cela, cliquez avec le bouton droit sur le bouton **Afficher le rapport** dans la barre d’outils. Dans la boîte de dialogue **Sélectionner un emplacement dans OneNote**, sélectionnez dans OneNote la section où vous souhaitez copier les données, puis cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

