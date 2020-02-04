---
title: 'Lync Server 2013 : restauration d’un serveur membre Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Si un serveur exécutant l’un des rôles serveur suivants ne fonctionne pas, suivez la procédure décrite dans cette rubrique pour restaurer le serveur. Si plusieurs serveurs échouent indépendamment, suivez la procédure pour chaque serveur.

  - serveur frontal

  - serveur de médiation

  - directeur

  - serveur de conversations permanentes

  - serveur Edge

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Pour restaurer un serveur membre

1.  Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que le serveur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.

3.  Recherchez le dossier d’installation ou le média de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de Setup. exe.

4.  Suivez l’Assistant déploiement pour effectuer les opérations suivantes :
    
    1.  Exécutez l' **étape 1 : installer le magasin de configuration local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2 : configurer ou supprimer les composants serveur Lync** pour installer le rôle serveur Lync Server.
    
    3.  Exécutez l' **étape 3 : demandez, installez ou attribuez des certificats** pour attribuer les certificats.
    
    4.  Exécutez l' **étape 4 : démarrer des services** pour démarrer des services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement pour le rôle de serveur que vous restaurez.

</div>

</div>

<span> </span>

</div>

</div>

</div>

