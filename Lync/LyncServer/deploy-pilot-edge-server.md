---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Lync Server 2013. Les processus de déploiement et de configuration de Lync Server 2013 sont très similaires à Lync Server 2010. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour obtenir la procédure détaillée, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.

As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.

**Pour définir un pool Edge**

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.
    
    ![Boîte de dialogue définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir le nouveau pool Edge")

3.  Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.
    
    ![Boîte de dialogue définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue définir le nom de domaine complet du pool Edge")

4.  Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP. Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge Lync Server 2010 hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Noms de domaine complets externes**, **Définir l’adresse IP interne** et **Définir l’adresse IP externe**.

6.  Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs Edge Lync Server 2010.
    
    ![Boîte de dialogue définir le tronçon suivant](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Boîte de dialogue définir le tronçon suivant")

7.  Dans la page **associer des pools frontaux ou des pools de médiation** , n’associez pas un pool à ce pool Edge pour le moment. Le trafic multimédia externe est actuellement routé via le serveur Edge Lync Server 2010 hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue pools frontaux associés](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Boîte de dialogue pools frontaux associés")

8.  Cliquez sur **Terminer**, puis sur **Publier** pour publier la topologie.

9.  Suivez les étapes décrites dans [install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.

Il est très important de suivre les instructions des rubriques déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.

Vous devez maintenant disposer d’un serveur Edge Lync Server 2010 hérité déployé en parallèle avec un déploiement de serveur Edge Lync Server 2013. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.

</div>

<span> </span>

</div>

</div>

</div>

