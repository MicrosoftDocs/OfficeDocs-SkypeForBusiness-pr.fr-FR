---
title: Déploiement du pool de pilotes Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Déploiement du pool de pilotes Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-22_

L’une des premières étapes requises pour la migration vers Lync Server 2013 consiste à déployer un pool de pilotes. Le pool de pilotes vous permet de tester la coexistence de Lync Server 2013 avec le déploiement de Lync Server 2010. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé l’ensemble des utilisateurs et des groupes vers Lync Server 2013.

Lorsque vous déployez un pool de pilotes, vous utilisez l’Assistant définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool de pilotes Lync Server 2013 que vous avez dans votre pool Lync Server 2010. Si vous avez déployé des serveurs d’archivage, de surveillance ou de System Center Operations Manager permettant d’archiver ou de surveiller votre environnement Lync Server 2010, et que vous voulez continuer à archiver ou à surveiller tout au long de la migration, vous devez également les déployer. fonctionnalités de votre environnement pilote. La version que vous avez déployée pour archiver ou surveiller votre environnement Lync Server 2010 ne capture pas de données dans votre environnement Lync Server 2013.

<div>


> [!NOTE]  
> La procédure suivante décrit les fonctionnalités et paramètres à envisager dans le cadre de votre processus global de déploiement de pool pilote. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. Pour consulter la procédure détaillée, voir le Guide de déploiement de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Pour déployer un pool de pilotes de Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Développez l’arborescence jusqu’à ce que vous atteigniez **Lync Server 2013** **Enterprise Edition**.

3.  Cliquez avec le bouton droit sur **Pools frontal pour Enterprise Edition**, puis sélectionnez **nouveau pool frontal**.
    
    ![Sous-menu de sélection de pool de serveurs du concepteur topologique] (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sous-menu de sélection de pool de serveurs du concepteur topologique")

4.  Entrez le nom de domaine complet (FQDN) du pool. Lors de la définition de votre pool de pilotes, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition Server. Lync Server 2013 ne nécessite pas que les fonctionnalités de votre pool pilote correspondent aux éléments déployés dans votre pool hérité.
    
    <div>
    

    > [!WARNING]  
    > Le pool ou le nom de domaine complet (FQDN) du serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool Lync Server 2010 actuellement déployé ou à tout autre serveur actuellement déployé.

    
    </div>
    
    ![Page de nom de domaine complet de l’Assistant définir le pool frontal] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Page de nom de domaine complet de l’Assistant définir le pool frontal")

5.  Dans la page **Sélectionner des fonctionnalités** , activez les cases à cocher des fonctionnalités que vous voulez inclure dans ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée multipartie, mais pas les cases à cocher Conférence rendez-vous (RTC), voix entreprise ou contrôle d’admission des appels. comme ils représentent les fonctionnalités de voix, de vidéo et de conférence de collaboration. Pour plus d’informations sur la sélection de fonctionnalités, voir [définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.
    
    ![Page de sélection des fonctionnalités du pool frontal] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page de sélection des fonctionnalités du pool frontal")

6.  Dans la page **Sélectionner des rôles de serveur** colocalisés, nous vous recommandons de Collocate le serveur de médiation dans Lync Server 2013. Lors de la fusion d’une topologie héritée avec Lync Server 2013, vous devez commencer par collocate le serveur de médiation Lync Server 2010. Après avoir fusionné les topologies et configuré le serveur de médiation Lync Server 2013, vous pouvez décider si vous souhaitez conserver le serveur de médiation colocalisé ou le modifier en serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Lync Server 2013 par la suite dans le cadre du déploiement. temps.
    
    ![Page de rôles de serveur en liste de choix] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page de rôles de serveur en liste de choix")

7.  Dans la page associez les **rôles de serveur à cette liste frontale** , pendant le déploiement du pool de pilotes, ne sélectionnez pas l’option **activer un pool Edge à utiliser par le composant multimédia de cette option de pool frontal** . Il s’agit d’une fonctionnalité que vous allez activer et mettre en ligne dans une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment.
    
    ![Associer des rôles de serveur à une page de pool frontal] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associer des rôles de serveur à une page de pool frontal")

8.  Dans la page **Sélectionner un serveur Office Web Apps** , cliquez sur **nouveau**, puis spécifiez le nom de domaine complet du serveur d’applications.
    
    ![Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server")

9.  Dans la page **définir la banque SQL Server** , lors de la définition de la banque SQL Server pour l’archivage et la surveillance de Lync Server, sélectionnez l’instance SQL Server créée précédemment pour lync Server 2013.
    
    ![Page définir l’archivage de SQL Server Store] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page définir l’archivage de SQL Server Store")

10. Pour publier votre topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **publier la topologie**.
    
    ![Générateur de topologie présentant une topologie configurée] (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Générateur de topologie présentant une topologie configurée")

11. Lorsque le processus de publication est terminé, cliquez sur **Terminer**.

Pour installer une copie locale du magasin de configuration et démarrer les services requis, voir [configuration de serveurs frontaux et de listes frontales pour Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.


</div>

<span> </span>

</div>

</div>

</div>

