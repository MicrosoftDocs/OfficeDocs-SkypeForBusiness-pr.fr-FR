---
title: 'Lync Server 2013: infrastructure à clé publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infrastructure à clé publique pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-13_

Microsoft Lync Server 2013 repose sur des certificats pour l’authentification du serveur et établit une chaîne de confiance entre les clients et les serveurs et entre les différents rôles de serveur. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003 infrastructure à clé publique (PKI) fournit l’infrastructure permettant d’établir et de valider cette chaîne de confiance.

Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Afin de garantir que les informations d’un certificat sont valides, celui-ci doit être émis par une autorité de certification (CA) approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.

Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.

Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.

<div>


> [!NOTE]  
> Toutes les autorités de certification publiques ne respectent pas les exigences des certificats Lync Server 2013. Nous vous conseillons de vous reporter à la liste des autorités de certification publiques approuvées pour vos besoins de certificats publics. Pour plus d’informations, reportez- <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>vous à la rubrique partenaires de certification de communications unifiées



</div>

<div>

## <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats

Lync Server 2013 nécessite que tous les certificats serveur contiennent un ou plusieurs points de distribution de la liste de révocation de certificats. Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit généralement d’une adresse HTTP sécurisée.

</div>

<div>

## <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé

Lync Server 2013 nécessite que tous les certificats serveur prennent en charge l’utilisation améliorée de l’utilisation de la clé pour l’utilisation de l’authentification du serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS. Il est possible d’avoir plusieurs entrées dans l’EKU, ce qui permet au certificat d’avoir plusieurs rôles.

<div>


> [!NOTE]  
> L’utilisation améliorée de l’authentification du client est requise pour les connexions MTLS sortantes à partir de Live Communications Server 2003 et de Live Communications Server 2005, mais elle n’est plus nécessaire. Toutefois, cette utilisation de l’utilisation améliorée doit être présente sur les serveurs Edge qui se connectent à AOL au moyen de la connectivité PIC (Public IM Connectivity).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

