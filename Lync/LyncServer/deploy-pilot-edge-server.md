---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge Lync Server 2013. Les processus de déploiement et de configuration de Lync Server 2013 sont similaires à Lync Server 2010. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. Pour obtenir la procédure détaillée, consultez la rubrique déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.

À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes. Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées.

**Définir un pool de bords**

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle liste de bord**.
    
    ![Boîte de dialogue définir la nouvelle réserve de bords](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir la nouvelle réserve de bords")

3.  Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.
    
    ![Définir la boîte de dialogue nom de domaine complet du pool de bords](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Définir la boîte de dialogue nom de domaine complet du pool de bords")

4.  Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP. Les fédérations de Fédération et XMPP sont actuellement routées via le serveur Edge Lync Server 2010 hérité. Ces fonctionnalités seront configurées lors de la phase de migration ultérieure.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Continuez à remplir les pages suivantes de l’Assistant : noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.

6.  Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de périphériques Lync Server 2010.
    
    ![Boîte de dialogue définir le saut suivant](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Boîte de dialogue définir le saut suivant")

7.  Dans la page **Associate front end ou pools de médiation** , n’associez pas un pool à ce pool d’arêtes pour le moment. Le trafic de médias externes est actuellement acheminé via le serveur Edge Lync Server 2010 hérité. Ce paramètre sera configuré lors de la phase de migration ultérieure.
    
    ![Boîte de dialogue Associate](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Boîte de dialogue Associate")

8.  Cliquez sur **Terminer** , puis **publiez** la topologie.

9.  Suivez les étapes décrites dans l' [article installer des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services.

Il est très important de suivre les recommandations contenues dans les rubriques déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur.

Vous devez maintenant disposer d’un serveur Edge Lync Server 2010 hérité déployé en parallèle avec un déploiement de serveur Edge Lync Server 2013. Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante.

</div>

<span> </span>

</div>

</div>

</div>

