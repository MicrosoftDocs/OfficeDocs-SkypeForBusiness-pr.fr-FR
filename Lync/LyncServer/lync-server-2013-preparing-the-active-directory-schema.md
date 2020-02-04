---
title: 'Lync Server 2013 : Préparation du schéma Active Directory'
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
ms.openlocfilehash: 572f531b57c504bda210f8f21298076428342b62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Préparation du schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-27_

Avant de commencer à préparer les services de domaine Active Directory, vous pouvez ouvrir les fichiers de schéma à l’aide d’un éditeur de texte, tel que le bloc-notes Windows, ou voir [extensions de schéma Active Directory, classes et attributs utilisés par Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) pour consulter toutes les extensions de schéma des services de domaine Active Directory qui seront modifiées pour lync Server 2013. Lync Server utilise quatre fichiers de schéma :

  - ExternalSchema. ldf, utilisé à des fins d’interopérabilité avec Microsoft Exchange Server

  - ServerSchema. ldf, qui est le fichier de schéma principal de Lync Server 2013

  - BackCompatSchema. ldf, utilisé à des fins d’interopérabilité avec les composants des versions précédentes

  - VersionSchema. ldf, qui est utilisé pour les informations de version du schéma préparé.

Tous les fichiers. ldf sont installés lors de la préparation du schéma, que vous passiez à partir d’une version précédente ou que vous effectuiez une nouvelle installation. Ces fichiers de schéma sont installés dans l’ordre présenté dans la liste précédente et se trouvent dans \\le\\dossier de schéma de support sur le média d’installation.

Les extensions de schéma Lync Server sont répliquées dans tous les domaines, ce qui a un impact sur le trafic réseau. Exécutez la préparation du schéma à la fois lorsque le niveau d’utilisation du réseau est faible.

<div>


> [!NOTE]  
> Si vous avez besoin d’ajouter la prise en charge de Microsoft® Office Communicator Mobile 2007 R2 pour Java et Microsoft® Office Communicator Mobile pour Nokia 1,0 vers votre déploiement Lync Server 2013, vous devez préparer le schéma Active Directory pour Microsoft Office Communications Server 2007 R2 lors de l’installation de Lync Server 2013. Pour le logiciel et la documentation nécessaires, <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>voir.



</div>

<div>

## <a name="adsi-edit"></a>Modification ADSI

L’éditeur d’interfaces de service Active Directory (ADSI Edit) est un outil d’administration AD DS qui vous permet de vérifier la préparation du schéma et la réplication.

ADSI Edit est installé par défaut lorsque vous installez le rôle AD DS pour définir un serveur comme contrôleur de domaine. Pour Windows Server 2008 et Windows Server 2008 R2, ADSI Edit (adsied. msc) est inclus dans les outils d’administration de serveur distant. Vous pouvez également installer le RSAT sur les serveurs de membres de domaine ou les serveurs autonomes. Le package RSAT est copié sur ces serveurs par défaut lors de l’installation de Windows, mais il n’est pas installé par défaut. Vous installez des outils individuels à l’aide du gestionnaire de serveur. La modification ADSI est incluse dans **Outils d’administration de rôles**, outils de services de **domaine Active Directory**, **outils de contrôleur de domaine Active Directory**.

Pour Windows Server 2003, l’édition ADSI est incluse dans les outils de support. Les outils de support sont disponibles sur le CD Windows Server 2003 dans \\le\\dossier Outils de support, ou vous pouvez les télécharger à partir des outils de support technique de Windows server 2003 Service [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)Pack 2 32-bit. Pour obtenir des instructions sur l’installation des outils d’assistance technique sur le CD du produit, voir la [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)section « installer les outils de support Windows » à l’adresse. Adsied. dll est enregistré automatiquement lorsque vous installez les outils de support. Toutefois, si vous avez copié les fichiers sur votre ordinateur, vous devez exécuter la commande **regsvr32** pour inscrire le fichier adsied. dll avant de pouvoir exécuter l’outil.

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

