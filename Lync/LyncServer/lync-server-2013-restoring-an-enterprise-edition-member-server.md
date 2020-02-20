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
ms.openlocfilehash: 9ec5172df20205d37bb79995280a2c50e3f8efc1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Si un serveur exécutant l’un des rôles serveur suivants échoue, suivez la procédure décrite dans cette rubrique pour restaurer le serveur. Si plusieurs serveurs connaissent une défaillance, appliquez la procédure à chaque serveur.

  - serveur frontal

  - Serveur de médiation

  - 48000b

  - serveur de conversations permanentes

  - Serveur Edge

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Pour restaurer un serveur membre

1.  Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que le serveur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.

3.  Accédez au dossier ou au support d’installation de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de amd64 Setup. exe.

4.  Utilisez l’Assistant Déploiement pour faire ce que suit :
    
    1.  Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer le rôle serveur Lync Server.
    
    3.  Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.
    
    4.  Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, reportez-vous à la documentation de déploiement du rôle serveur que vous restaurez.

</div>

</div>

<span> </span>

</div>

</div>

</div>

