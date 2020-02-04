---
title: 'Lync Server 2013 : publier la base de données de localisation'
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
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Publier la base de données de localisation à partir de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Le client ne pourra accéder aux nouveaux emplacements ajoutés à la base de données d’emplacements qu’une fois qu’ils seront publiés.

Pour plus d’informations, consultez la documentation de Lync Server Management Shell pour l’applet de commande suivante :

  - **Publish-CsLisConfiguration**

Si vous utilisez des passerelles ELIN, vous devez également charger les numéros d’identification de l’emplacement en cas d’urgence dans la base de données ALI (Automatic Location Identification) de votre opérateur de réseau téléphonique commuté (RTC). Celui-ci peut exiger l’utilisation d’un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez l’opérateur RTC. Vous pouvez exporter les enregistrements de la base de données de service d’information d’emplacement et les mettre en forme selon les besoins.

<div>

## <a name="to-publish-the-location-database"></a>Pour publier la base de données d’emplacements

  - Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

  - Exécutez l’applet de commande ci-dessous pour publier la base de données d’emplacements.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

