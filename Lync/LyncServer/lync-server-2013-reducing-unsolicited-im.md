---
title: 'Lync Server 2013 : réduction des messages instantanés non sollicités'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c8aaf86eca6751dbf16ae67d39d0bccd341422e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Réduction des messages instantanés non sollicités pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-05_

L’application de filtre de message instantané intelligent permet de protéger votre déploiement Microsoft Lync Server 2013 contre les virus les plus courants avec une dégradation minimale de l’expérience utilisateur. Le filtre de message instantané intelligent fournit les éléments suivants :

  - Filtrage d’URL amélioré

  - Filtrage amélioré de transfert de fichiers

Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de systèmes d’extrémité inconnus externes au pare-feu d’entreprise. Vous configurez des filtres en spécifiant les critères à utiliser pour déterminer les éléments qui doivent être bloqués, tels que les messages instantanés contenant des liens hypertexte et des fichiers avec des extensions spécifiques.

Avant de déployer l’application de filtre de message instantané intelligent, vous devez comprendre comment les options de filtrage sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 à un autre. L’application de ces options de filtrage s’effectue toujours de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations. Cette cohérence s’applique à la façon dont l’avis personnalisé et les textes d’avertissement sont insérés dans les messages et envoyés sur plusieurs serveurs.

L’option de filtrage recommandé est d’autoriser les messages instantanés avec des liens hypertexte mais de demander au filtre de messagerie instantanée intelligent de désactiver le lien en insérant un trait de soulignement avant lui. Si vous choisissez cette option, vous avez la possibilité supplémentaire de rédiger une notification aux utilisateurs qui apparaît au début de chaque message instantané contenant un lien hypertexte.

Une deuxième option de filtrage consiste à autoriser les messages instantanés avec des liens hypertexte non modifiés. Si vous choisissez cette option, vous disposez de l’option supplémentaire (recommandé) pour rédiger un avertissement aux utilisateurs qui sont insérés dans chaque message.

Une troisième option consiste à bloquer tous les messages instantanés qui contiennent des liens hypertexte. Si vous choisissez cette option, le serveur envoie un avertissement à l’utilisateur. Vous devez rédiger cet avertissement.

</div>

<span> </span>

</div>

</div>

</div>

