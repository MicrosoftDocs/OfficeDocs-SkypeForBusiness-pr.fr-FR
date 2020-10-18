---
title: 'Lync Server 2013 : analyse du rapport de certificats'
description: 'Lync Server 2013 : analyse du rapport de certificats.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2133e2f70c78217788d84251c2035a9115bc3283
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578460"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a>Consultation du rapport Certificates dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le rapport Certificates contient tous les certificats requis dans le déploiement de Lync Server 2013 recommandé. Les comptes de l’outil de planification pour les noms de sujet et les autres noms de sujet entrés. Le texte par défaut laissé non modifié peut représenter un défi potentiel pour l’équipe responsable de la demande et de l’émission des certificats. Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis. Si l’infrastructure ne dispose pas d’une PKI interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public. Les champs EKU et Affecter à du rapport sont très utiles pour connaître ce que doivent être l’objectif et l’emplacement de chaque certificat.

![Rapport d’administration des certificats](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapport d’administration des certificats")

Examinez attentivement et assurez-vous de bien comprendre l’utilisation et l’objectif de chaque certificat dans le déploiement. En cas de question sur le rôle d’un certificat, déterminez le serveur ou le service qui parle. Les certificats dans Lync Server 2013 sont utilisés à deux fins principales :

  - Mutual Transport Layer Security (MTLS) : les ordinateurs impliqués dans la communication présentent chacun un certificat qui prouve leur identité sur un autre ordinateur. Il s’agit de l’authentification du serveur. La communication ne peut pas commencer tant que chaque ordinateur n’approuve pas l’identité de l’autre ordinateur.

  - Chiffrement – Le chiffrement (Secure Sockets Layer ou SSL, et Transport Layer Security ou TLS) est un moyen très utile de sécuriser les communications, de garantir la confidentialité et de créer un système sûr de communication et de collaboration.

<div>

## <a name="see-also"></a>Voir aussi


[Examen des rapports de l’administrateur dans Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

