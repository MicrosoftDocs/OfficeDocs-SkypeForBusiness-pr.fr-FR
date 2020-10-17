---
title: 'Lync Server 2013 : composants utilisés par la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502361"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Composants utilisés par la prise d’appel de groupe dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

La prise d’appel de groupe est automatiquement déployée lorsque vous déployez voix entreprise et l’application de parcage d’appel. Vous activez la prise d’appel de groupe en configurant la table d’orbites de parcage d’appel avec des plages de numéros séparées comme numéros de groupe de prise d’appel, puis en affectant des groupes de prise d’appel et en activant les utilisateurs pour la prise d’appel de groupe. Les composants Lync Server suivants prennent en charge la prise d’appel de groupe :

  - **Service**     d’application Application service fournit une plateforme permettant de déployer, d’héberger et de gérer des applications de communications unifiées, telles que l’application de parcage d’appel. Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.

  - Application de parcage d' **appel**     L’application de parcage d’appel est l’une des applications de communications unifiées hébergées par le service d’application. La prise d’appel de groupe est basée sur l’application de parcage d’appel.

  - **Lync Server Management Shell**     Vous utilisez Lync Server Management Shell pour gérer les groupes de prise d’appel de groupe.

  - Outil de kit de **ressources SEFAUtil**     Vous utilisez l’utilitaire d’activation de fonctionnalité d’extension secondaire (SEFAUtil) pour attribuer des utilisateurs à un groupe de prise d’appel et pour activer ou désactiver la prise d’appel pour les utilisateurs.

</div>

<span> </span>

</div>

</div>

</div>

