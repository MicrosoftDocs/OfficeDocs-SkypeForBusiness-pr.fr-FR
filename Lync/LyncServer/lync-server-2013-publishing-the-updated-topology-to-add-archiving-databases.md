---
title: 'Lync Server 2013 : publication de la topologie mise à jour pour ajouter des bases de données d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0d12b1b4195e57fc289d11eb54f24903d05ea26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Publication de la topologie mise à jour pour ajouter des bases de données d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Après avoir effectué la mise à jour de votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central avant de pouvoir configurer et utiliser l’archivage. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.

<div>

## <a name="to-publish-your-updated-topology"></a>Pour publier votre topologie mise à jour

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte possédant des droits d’utilisateur équivalents).
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un serveur à la topologie. vous devez utiliser un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> et qui dispose des autorisations de contrôle total (en lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers 2013 Lync Server (c’est-à-dire, le générateur de topologie peut configurer la liste de contrôle d’accès discrétionnaire requise). ou un compte disposant de droits équivalents.

    
    </div>

2.  Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du générateur de topologie.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. Pour plus d’informations sur les autorisations et les droits d’administrateur requis, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A> dans la documentation de déploiement.<BR>Seules les bases de données sur des serveurs SQL Server dédiés peuvent être installées à l’aide du générateur de topologie. Les bases de données sur des serveurs SQL Server colocalisées avec d’autres composants serveur doivent être installés en exécutant la configuration locale sur cet ordinateur.

    
    </div>

6.  Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-support-for-archiving.md">configuration de la prise en charge de l’archivage dans Lync Server 2013</A> dans la documentation de déploiement.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

