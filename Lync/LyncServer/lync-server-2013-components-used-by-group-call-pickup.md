---
title: 'Lync Server 2013: composants utilisés par le prélèvement d’appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3583ee73c78a78317b1808bde395f76dcae85149
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Composants utilisés par le prélèvement d’appels de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

La prise d’appel de groupe est déployée automatiquement lors du déploiement de l’application voix entreprise et de l’application de parc d’appels. Vous pouvez activer le prélèvement d’appels de groupe en configurant la table orbite du parc d’appels avec des plages de numéros distinctes désignés comme numéros de groupe de capture d’appel, puis en attribuant aux utilisateurs la possibilité d’appeler les groupes de capture et en permettant aux utilisateurs de procéder à un appel de groupe. Les composants Lync Server suivants prennent en charge la cueillette des appels de groupe:

  - ****   Le service d’application de service d’application fournit une plateforme de déploiement, d’hébergement et de gestion d’applications de communications unifiées, telles que l’application de parc d’appels. Le service d’application est automatiquement installé sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server.

  - **Application de parc d’appels**   l’application de parc d’appels est l’une des applications de communications unifiées hébergées par le service d’application. Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels.

  - **Lync Server Management Shell**   vous utilisez Lync Server Management Shell pour gérer les groupes de capture d’appels de groupe.

  - **Outil du kit de ressources SEFAUtil**   vous utilisez l’utilitaire d’activation de l’extension secondaire (SEFAUtil) pour attribuer des utilisateurs à un groupe de cueillette d’appel et activer ou désactiver la fonction de cueillette des appels pour les utilisateurs.

</div>

<span> </span>

</div>

</div>

</div>

