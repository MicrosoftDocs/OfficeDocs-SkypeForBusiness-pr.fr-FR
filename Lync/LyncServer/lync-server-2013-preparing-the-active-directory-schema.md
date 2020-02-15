---
title: 'Lync Server 2013 : préparation du schéma Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d98f7ba4ac0f2efe8a78ebcaacdc966ac5fdf3a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Préparation du schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-27_

Avant de commencer à préparer les services de domaine Active Directory, vous pouvez ouvrir les fichiers de schéma à l’aide d’un éditeur de texte, tel que le bloc-notes Windows, ou consulter les [attributs, les classes et les extensions de schéma Active Directory utilisés par Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) pour examiner toutes les extensions de schéma des services de domaine Active Directory qui seront modifiées pour Lync Server 2013. Lync Server utilise quatre fichiers de schéma :

  - ExternalSchema. ldf, qui est utilisé pour l’interopérabilité avec Microsoft Exchange Server

  - ServerSchema. ldf, qui est le fichier de schéma Lync Server 2013 principal

  - BackCompatSchema.ldf, qui est utilisé pour l’interopérabilité avec des composants de versions précédentes

  - VersionSchema.ldf, qui est utilisé pour les informations de version du schéma préparé

Tous les fichiers .ldf sont installés au cours de la préparation du schéma, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation. Ces fichiers de schéma sont installés dans l’ordre indiqué dans la liste précédente et se trouvent dans \\le\\dossier de schéma de prise en charge sur le support d’installation.

Les extensions de schéma Lync Server sont répliquées dans tous les domaines, ce qui a un impact sur le trafic réseau. Exécutez la préparation du schéma lorsque l’utilisation du réseau est basse.

<div>


> [!NOTE]  
> Si vous devez ajouter la prise en charge pour les clients mobiles Microsoft® Office Communicator 2007 mobile R2 pour Java et Microsoft® Office Communicator Mobile pour Nokia 1,0 à votre déploiement Lync Server 2013, vous devez préparer le schéma Active Directory pour Microsoft Office Communications Server 2007 R2 lors de l’installation de Lync Server 2013. Pour obtenir les logiciels et la documentation nécessaires <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>, reportez-vous à.



</div>

<div>

## <a name="adsi-edit"></a>Éditeur ADSI

L’Éditeur ADSI (Active Directory Service Interfaces) est un outil d’administration AD DS qui vous permet de vérifier la préparation et la réplication du schéma.

L’Éditeur ADSI est installé par défaut lorsque vous installez le rôle AD DS pour faire d’un serveur un contrôleur de domaine. Pour Windows Server 2008 et Windows Server 2008 R2, ADSI Edit (adsiedit. msc) est inclus dans les outils d’administration de serveur distant (RSAT). Vous pouvez également installer les outils d’administration de serveur distant sur des serveurs membres du domaine ou des serveurs autonomes. Le package des outils d’administration de serveur distant est copié par défaut sur ces serveurs lorsque vous installez Windows, mais il n’est pas installé par défaut. Utilisez le Gestionnaire de serveur pour installer chaque outil. L’éditeur ADSI est inclus sous **Outils d’administration de rôles**, **Outils des services de domaine Active Directory**, **Outils de contrôleur de domaine Active Directory**.

Pour Windows Server 2003, l’Éditeur ADSI fait partie des outils de support. Les outils de support sont disponibles à partir du CD-ROM Windows \\Server\\2003 dans le dossier des outils de support, ou vous pouvez les télécharger à partir de « Windows server 2003 Service [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)Pack 2 32-bit Support Tools » sur le site. Les instructions d’installation des outils de support à partir du CD-ROM du produit sont disponibles à l' [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)adresse « installer les outils de support Windows » à l’adresse. Adsiedit.dll est inscrit automatiquement lorsque vous installez les outils de support. Toutefois, si vous avez copié les fichiers sur votre ordinateur, vous devez exécuter la commande **regsvr32** pour inscrire le fichier adsiedit.dll avant de pouvoir exécuter l’outil.

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exécution de la préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

