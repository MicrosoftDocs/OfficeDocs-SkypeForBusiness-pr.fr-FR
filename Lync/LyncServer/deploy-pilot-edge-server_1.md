---
title: Déploiement du serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Déploiement du serveur Edge pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Lync Server 2013. Cette section met en évidence les points clés que vous devez prendre en compte dans le cadre de votre déploiement pilote de pool Edge. Pour obtenir la procédure détaillée, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.

À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge**, examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées.

**Pour définir un pool Edge**

1.  Ouvrez la topologie du pool pilote à l’aide du générateur de topologie.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.
    
    ![Boîte de dialogue définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir le nouveau pool Edge")

3.  Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.
    
    ![Boîte de dialogue définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue définir le nom de domaine complet du pool Edge")

4.  Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP. Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge Office Communications Server 2007 R2 hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Sélectionner les options IP**, noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.

6.  Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs Edge Lync Server 2013.
    
    ![Boîte de dialogue définir un nouveau pool de serveurs Edge, liste Pool du tronçon suivant](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de serveurs Edge, liste Pool du tronçon suivant")

7.  Dans la page **Pools frontaux associés** , n’associez pas un pool à ce pool Edge pour le moment. Le trafic multimédia externe est actuellement routé via le serveur Edge Office Communications Server 2007 R2 hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue définir un nouveau pool de serveurs Edge](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de serveurs Edge")

8.  Cliquez sur **Terminer**, puis sur **Publier** pour publier la topologie.

9.  Suivez les étapes décrites dans [install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.

Il est très important de suivre les instructions des rubriques déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.

Vous devez maintenant disposer d’un déploiement de serveur Edge Office Communications Server 2007 R2 hérité, indiqué par la présence du BackCompatSite, en parallèle à un déploiement de serveur Edge Lync Server 2013. La Fédération est configurée pour utiliser le directeur Office Communications Server 2007 R2. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.

![Générateur de topologies affichant le serveur Edge OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Générateur de topologies affichant le serveur Edge OCS")

</div>

<span> </span>

</div>

</div>

</div>

