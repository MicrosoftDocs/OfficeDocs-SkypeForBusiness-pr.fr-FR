---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge Lync Server 2013. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool de périphériques pilote. Pour obtenir la procédure détaillée, consultez la rubrique déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.

À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes. Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées.

**Définir un pool de bords**

1.  Ouvrez la topologie de pool pilote à l’aide du générateur de topologie.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle liste de bord**.
    
    ![Boîte de dialogue définir la nouvelle réserve de bords] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir la nouvelle réserve de bords")

3.  Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.
    
    ![Définir la boîte de dialogue nom de domaine complet du pool de bords] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Définir la boîte de dialogue nom de domaine complet du pool de bords")

4.  Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP. La Fédération des fédérations et XMPP est actuellement routée via le serveur Edge Office Communications Server 2007 R2 hérité. Ces fonctionnalités seront configurées lors de la phase de migration ultérieure.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Continuez à compléter les pages suivantes de l’Assistant: **sélectionnez Options IP**, noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.

6.  Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de périphériques Lync Server 2013.
    
    ![Boîte de dialogue définir un nouveau pool de bords, liste de pools de tronçons suivants] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de bords, liste de pools de tronçons suivants")

7.  Dans la page **Associate front end pools** , n’associez pas un pool à ce pool d’arêtes pour le moment. Le trafic de médias externes est actuellement acheminé via le serveur Edge Office Communications Server 2007 R2. Ce paramètre sera configuré lors de la phase de migration ultérieure.
    
    ![Boîte de dialogue définir un nouveau pool de bords] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de bords")

8.  Cliquez sur **Terminer** , puis **publiez** la topologie.

9.  Suivez les étapes décrites dans l' [article installer des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services.

Il est très important de suivre les recommandations contenues dans les rubriques déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur.

Pour le moment, vous devez disposer d’un déploiement d’Office Communications Server 2007 R2 d’ancienne génération, indiqué par la présence de BackCompatSite, parallèlement à un déploiement Lync Server 2013 Edge Server. La Fédération est configurée pour utiliser le directeur Office Communications Server 2007 R2. Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante.

![Générateur de topologie montrant un serveur Edge OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Générateur de topologie montrant un serveur Edge OCS")

</div>

<span> </span>

</div>

</div>

</div>

