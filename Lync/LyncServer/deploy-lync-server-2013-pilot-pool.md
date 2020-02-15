---
title: Déployer le pool pilote Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aa76856725457a90d6c9309687e39cdcc815954
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Déployer le pool pilote Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-22_

L’une des premières étapes requises pour la migration vers Lync Server 2013 consiste à déployer un pool pilote. Le pool pilote est l’endroit où vous testez la coexistence de Lync Server 2013 avec votre déploiement Lync Server 2010. La coexistence est un état temporaire qui dure jusqu’à ce que vous ayez déplacé tous les utilisateurs et pools vers Lync Server 2013.

Lorsque vous déployez un pool pilote, vous utilisez l’Assistant Définir un nouveau pool frontal. Vous devez déployer les mêmes fonctionnalités et charges de travail dans votre pool de pilotes Lync Server 2013 que vous avez dans votre pool Lync Server 2010. Si vous avez déployé le serveur d’archivage, le serveur de surveillance ou System Center Operations Manager pour l’archivage ou la surveillance de votre environnement Lync Server 2010, et que vous souhaitez continuer l’archivage ou la surveillance pendant la migration, vous devez également déployer ces fonctionnalités de votre environnement pilote. La version que vous avez déployée pour archiver ou surveiller votre environnement Lync Server 2010 ne capture pas les données dans votre environnement Lync Server 2013.

<div>


> [!NOTE]  
> La procédure qui suit traite des fonctionnalités et paramètres à considérer dans le cadre du processus de déploiement général de votre pool pilote. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour obtenir la procédure détaillée, reportez-vous au Guide de déploiement de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Pour déployer un pool pilote Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Développez l’arborescence jusqu’à ce que vous atteigniez les **Pools frontaux Enterprise Edition**de **Lync Server 2013** .

3.  Cliquez avec le bouton droit sur **Pools frontaux Enterprise Edition** et sélectionnez **Nouveau pool frontal**.
    
    ![Sous-menu de sélection de pool de serveurs du générateur de topologies](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Sous-menu de sélection de pool de serveurs du générateur de topologies")

4.  Entrez le nom de domaine complet du pool. Lorsque vous définissez votre pool pilote, vous pouvez choisir de déployer un pool frontal Enterprise Edition ou un serveur Standard Edition. Lync Server 2013 ne requiert pas que les fonctionnalités de pool pilote correspondent à ce qui a été déployé dans votre pool hérité.
    
    <div>
    

    > [!WARNING]  
    > Le nom de domaine complet du pool ou serveur que vous définissez pour le pool pilote doit être unique. Il ne peut pas correspondre au nom du pool Lync Server 2010 actuellement déployé ou à tous les autres serveurs actuellement déployés.

    
    </div>
    
    ![Page définir le nom de domaine complet de l’assistant nouveau pool frontal](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Page définir le nom de domaine complet de l’assistant nouveau pool frontal")

5.  Dans la page **Sélectionner les fonctionnalités**, activez les cases à cocher correspondant aux fonctionnalités souhaitées pour ce pool frontal. Par exemple, si vous déployez uniquement les fonctionnalités de messagerie instantanée et de présence, activez la case à cocher Conférence pour autoriser la messagerie instantanée à plusieurs, mais n’activez pas les cases à cocher Conférence rendez-vous (PSTN), Voix Entreprise ou Contrôle d’admission des appels, car elles représentent les fonctionnalités de voix, de vidéo et de conférence collaborative. Pour plus d’informations sur la sélection des fonctionnalités, reportez-vous à la rubrique [define and Configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) dans la documentation de déploiement.
    
    ![Page Sélectionner les fonctionnalités du pool frontal](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Page Sélectionner les fonctionnalités du pool frontal")

6.  Sur la page **Sélectionner des rôles serveur colocalisés** , nous vous recommandons de colocaliser le serveur de médiation dans Lync Server 2013. Lors de la fusion d’une topologie héritée avec Lync Server 2013, nous vous recommandons de commencer par colocaliser le serveur de médiation Lync Server 2010. Après avoir fusionné les topologies et configuré le serveur de médiation Lync Server 2013, vous pouvez décider s’il faut conserver le serveur de médiation colocalisé ou le remplacer par un serveur autonome lorsque vous déplacez le rôle de serveur de médiation vers Lync Server 2013 plus tard dans le déploiement. traitement.
    
    ![Page pool frontal-sélection de rôles serveur colocalisés](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Page pool frontal-sélection de rôles serveur colocalisés")

7.  Dans la page **Rôles serveur associés à ce pool frontal**, lors du déploiement du pool pilote, ne sélectionnez pas l’option **Activer un pool Edge à utiliser avec le composant média de ce pool frontal**. Il s’agit d’une fonctionnalité que vous activerez et mettrez en ligne lors d’une phase ultérieure de la migration. Laissez ce paramètre désactivé pour le moment.
    
    ![Rôles serveur associés avec page de pool frontal](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Rôles serveur associés avec page de pool frontal")

8.  Dans la page **Sélectionner un serveur Office Web Apps**, cliquez sur **Nouveau**, puis indiquez le nom de domaine complet du serveur d’applications.
    
    ![Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Définir de nouvelles propriétés de nom de domaine complet Office Web Apps Server")

9.  Sur la page **définir le magasin SQL Server d’archivage** , lors de la définition du magasin SQL Server pour l’archivage et la surveillance de Lync Server, sélectionnez l’instance SQL Server créée précédemment pour lync Server 2013.
    
    ![Page définir le magasin SQL Server d’archivage](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Page définir le magasin SQL Server d’archivage")

10. Pour publier votre topologie, cliquez avec le bouton droit sur le nœud **Lync Server**, puis cliquez sur **Publier la topologie**.
    
    ![Générateur de topologie affichant une topologie configurée](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Générateur de topologie affichant une topologie configurée")

11. Au terme du processus, cliquez sur **Terminer**.

Pour installer une copie locale du magasin de configuration et démarrer les services requis, voir [Setting Up Front End Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) dans la documentation de déploiement.


</div>

<span> </span>

</div>

</div>

</div>

