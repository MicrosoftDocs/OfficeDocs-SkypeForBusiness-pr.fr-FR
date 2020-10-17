---
title: 'Lync Server 2013 : configuration de la Sign-In automatique des clients pour utiliser le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522961"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>Configuration de la Sign-In automatique des clients pour utiliser le directeur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Lorsque vous déployez un serveur Lync Server 2013, un directeur ou un pool de directeurs, nous vous recommandons d’utiliser les Sign-In client automatiques en guise de meilleures pratiques. Pour plus d’informations sur la configuration des serveurs DNS pour la connexion automatique des clients, voir [configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) dans la documentation de planification.

Si vous avez déjà déployé l’ouverture de session client automatique, consultez les sections suivantes pour la configurer sur votre ou vos directeurs.

<div>

## <a name="single-director-instance"></a>Instance de directeur unique

Si le client automatique Sign-In est déjà déployé et qu’il pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le directeur.

</div>

<div>

## <a name="director-pool"></a>Pool directeur

Si le client automatique Sign-In est déjà déployé et qu’il pointe vers un serveur frontal ou un pool frontal, vous devez modifier l’enregistrement DNS SRV de sorte qu’il pointe vers le pool directeur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

