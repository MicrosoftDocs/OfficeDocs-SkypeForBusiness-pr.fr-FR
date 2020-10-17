---
title: 'Lync Server 2013 : infrastructure à clé publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512411"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infrastructure de clé publique pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-13_

Microsoft Lync Server 2013 repose sur des certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles serveur. L’infrastructure à clé publique (PKI) Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003 fournit l’infrastructure permettant d’établir et de valider cette chaîne de confiance.

Les certificats sont des identifiants numériques. Ils identifient un serveur à l’aide de son nom et spécifient ses propriétés. Pour vous assurer que les informations sur un certificat sont valides, le certificat doit être émis par une autorité de certification approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement à d’autres clients et serveurs sur un réseau privé, l’autorité de certification peut être une autorité de certification d’entreprise. Si le serveur communique avec des entités en dehors du réseau privé, une autorité de certification publique peut être nécessaire.

Même si les informations du certificat sont valides, il doit être possible de vérifier si le serveur soumettant le certificat est réellement celui qu’il représente. C’est à ce niveau qu’intervient l’infrastructure à clé publique Windows.

Chaque certificat est lié à une clé publique. Le serveur nommé dans le certificat détient une clé privée correspondante qu’il est le seul à connaître. Lorsqu’un client ou un serveur se connecte, il utilise la clé publique pour chiffrer une information aléatoire qu’il envoie au serveur. Si le serveur déchiffre les informations et les renvoie sous forme de texte simple, l’entité connectée est sûre que le serveur détient la clé privée du certificat et qu’il s’agit donc bien du serveur nommé dans le certificat.

<div>


> [!NOTE]  
> Toutes les autorités de certification publiques ne respectent pas les exigences des certificats Lync Server 2013. Nous vous recommandons de vous reporter à la liste des fournisseurs d’autorités de certification publiques certifiées selon vos besoins de certificats publics. Pour plus d’informations, consultez la page relative aux partenaires de certificat de communications unifiées <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .



</div>

<div>

## <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats (CRL)

Lync Server 2013 nécessite que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Il s’agit d’emplacements à partir desquels il est possible de télécharger des listes de révocation de certificats afin de vérifier si un certificat a été révoqué depuis son émission et s’il est toujours dans sa période de validité. Un point de distribution de liste de révocation de certificats figure dans les propriétés du certificat sous forme d’URL, généralement HTTP sécurisée.

</div>

<div>

## <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé

Lync Server 2013 nécessite que tous les certificats de serveur prennent en charge l’utilisation améliorée de la clé (EKU) pour l’authentification du serveur. La configuration du champ EKU pour l’authentification de serveurs signifie que le certificat est valide pour l’authentification des serveurs. L’utilisation améliorée de la clé est essentielle pour MTLS. Le champ EKU peut contenir plusieurs entrées, ce qui permet d’activer le certificat à plusieurs fins.

<div>


> [!NOTE]  
> L’EKU d’authentification client était requis pour les connexions MTLS sortantes provenant de Live Communications Server 2003 et Live Communications Server 2005, mais il n’est plus nécessaire. Toutefois, cet EKU doit figurer sur les serveurs de périphérie qui se connectent à AOL par le biais de la solution PIC.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

