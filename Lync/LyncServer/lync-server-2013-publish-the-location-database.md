---
title: 'Lync Server 2013 : publication de la base de données d’emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d524f8551561a4c7fb61abdaa6ab15bf2c111de9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Publier la base de données d’emplacements à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Les nouveaux emplacements ajoutés à la base de données d’emplacements ne seront pas mis à la disposition du client tant qu’ils n’auront pas été publiés.

Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour l’applet de commande suivante :

  - **Publish-CsLisConfiguration**

Si vous utilisez des passerelles ELIN (Emergency location Identification Number), vous devez également télécharger le numéros vers la base de données ALI (Automatic location identifier) de votre opérateur de téléphonie commuté (PSTN). Votre opérateur RTC peut exiger que vous utilisiez un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez votre opérateur RTC. Vous pouvez exporter les enregistrements à partir de la base de données du service informations d’emplacement et les formater le cas échéant.

<div>

## <a name="to-publish-the-location-database"></a>Pour publier la base de données d’emplacements

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

  - Exécutez l’applet de commande suivante pour publier la base de données d’emplacements.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

