---
title: 'Lync Server 2013 : réduction des messages instantanés non sollicités'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Réduction des messages instantanés non sollicités pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-05_

L’application de filtre de messages instantanés intelligents vous aide à protéger votre déploiement de Microsoft Lync Server 2013 contre les virus les plus fréquents avec une dégradation minimale de l’interface utilisateur. Ce filtre fournit les éléments suivants:

  - Amélioration du filtrage d’URL

  - Amélioration du filtrage du transfert de fichiers

Utilisez le filtre de message instantané intelligent pour configurer des filtres permettant de bloquer les messages instantanés non sollicités ou potentiellement dangereux de points de terminaison inconnus en dehors du pare-feu de l’entreprise. Vous pouvez configurer des filtres en spécifiant les critères à utiliser pour déterminer ce qui devrait être bloqué (par exemple, les messages instantanés contenant des liens hypertexte et des fichiers avec des extensions spécifiques).

Avant de déployer l’application de filtre de messages INSTANTANÉs intelligents, vous devez comprendre comment les options de filtre sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre. La façon dont ces options de filtrage sont appliquées est cohérente, qu’il s’agisse de serveurs au sein d’une organisation unique ou de limites de l’organisation. Cette cohérence s’applique au mode d’insertion des avis personnalisés et des textes d’avertissement dans les messages et envoyés sur plusieurs serveurs.

L’option de filtrage recommandée consiste à autoriser les messages instantanés avec des liens hypertexte, mais ils nécessitent le filtre de messagerie instantanée intelligent pour désactiver le lien en insérant un trait de soulignement. Si vous choisissez cette option, vous avez la possibilité d’ajouter un avis aux utilisateurs qui s’affichent au début de chaque message instantané contenant un lien hypertexte.

Une deuxième option de filtrage consiste à autoriser les messages instantanés comportant des liens hypertexte non modifiés. Si vous choisissez cette option, vous avez la possibilité d’utiliser l’option supplémentaire (recommandée) pour composer un avertissement aux utilisateurs insérés dans chaque message.

Une troisième option consiste à bloquer tous les messages instantanés qui contiennent des liens hypertexte. Si vous choisissez cette option, le serveur envoie un message d’avertissement à l’utilisateur. Vous devez rédiger cet avertissement.

</div>

<span> </span>

</div>

</div>

</div>

