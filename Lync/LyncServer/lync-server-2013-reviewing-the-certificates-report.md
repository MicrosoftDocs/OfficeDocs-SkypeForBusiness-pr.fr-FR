---
title: 'Lync Server 2013: examen du rapport sur les certificats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a83167576746d3f90d96658b0dd3d65815f5375
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Examen du rapport certificats dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Le rapport certificats contient tous les certificats requis dans le déploiement de Lync Server 2013 recommandé. Les comptes d’outils de planification pour les noms d’objet et les noms de remplacement d’objet entrés. Le texte par défaut non modifié peut constituer un défi potentiel pour l’équipe qui est responsable de la demande et de l’émission des certificats. Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis. Si l’infrastructure ne dispose pas d’une infrastructure à clé publique (PKI) interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public. Les champs Utilisation améliorée de la clé (EKU) et Affecter à du rapport sont très utiles pour comprendre ce que doivent être l’objectif et l’emplacement de chaque certificat.

![Rapport d’administration des certificats] (images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapport d’administration des certificats")

Examinez et étudiez attentivement l’utilisation et l’objectif de chaque certificat dans le déploiement. En cas de doute sur le rôle d’un certificat, déterminez les éléments avec lesquels le serveur ou le service communique. Les certificats de Lync Server 2013 sont utilisés pour deux fonctions principales:

  - Mutual Transport Layer Security (MTLS) – Les ordinateurs impliqués dans la communication présentent chacun un certificat qui prouve leur identité à un autre ordinateur. On appelle cela l’authentification serveur. La communication ne peut pas commencer tant que chaque ordinateur n’a pas approuvé l’identité de l’autre ordinateur.

  - Chiffrement – Le chiffrement (Secure Sockets Layer ou SSL, et Transport Layer Security ou TLS) est un moyen très utile de sécuriser les communications, de garantir la confidentialité et de créer un système sûr de communication et de collaboration.

<div>

## <a name="see-also"></a>Voir aussi


[Consultation des rapports de l’administrateur dans Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

