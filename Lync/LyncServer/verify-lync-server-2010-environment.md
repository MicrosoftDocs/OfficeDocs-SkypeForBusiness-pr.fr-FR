---
title: Vérifier l’environnement Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b04170df1a616aec595f72dce74cd15e8059b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Vérifier l’environnement Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Avant de déployer Lync Server 2013 dans un état de coexistence avec Lync Server 2010, vous devez vérifier que les services Lync Server 2010 ont été configurés et démarrés. Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool pilote Lync Server 2013. Avant de déployer Microsoft Lync Server 2013 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée. La vérification de votre déploiement hérité de Lync Server 2010 implique les opérations suivantes :

  - Vérification du démarrage des services Lync Server 2010

  - Examen de la topologie et des utilisateurs dans Lync Server 2010.

  - Vérification des paramètres de fédération et du serveur Edge

  - Vérification des services XMPP et des partenaires fédérés

**Vérifier que les services Lync Server 2010 sont démarrés**

1.  À partir du serveur frontal Lync Server 2010, accédez à l’applet\\services d’administration.

2.  Vérifiez que les services suivants sont exécutés sur le serveur frontal :
    
    ![Liste des services exécutés sur un serveur frontal](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste des services exécutés sur un serveur frontal")

**Consultez la topologie Lync Server 2010 dans le panneau de configuration Lync Server**

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Sélectionnez **Topologie**. Vérifiez que les différents serveurs de votre déploiement Lync Server 2010 sont répertoriés.
    
    ![Page topologie du panneau de configuration Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Page topologie du panneau de configuration Lync Server 2010")

**Pour consulter les utilisateurs de Lync Server 2010 dans le panneau de configuration Lync Server**

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Sélectionnez **Utilisateurs**, puis cliquez sur **Rechercher**.

3.  Vérifiez que la colonne pool de serveurs d' **inscriptions** pointe vers le pool Lync Server 2010 pour chaque utilisateur mentionné.
    
    ![Panneau de configuration Lync Server 2010 répertoriant les utilisateurs](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panneau de configuration Lync Server 2010 répertoriant les utilisateurs")

**Pour vérifier les paramètres de Fédération et de périmètre Lync Server 2010**

1.  Démarrez le Générateur de topologie.

2.  Sélectionnez **Télécharger la topologie à partir du déploiement existant**.

3.  Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier par défaut (.tbxml).

4.  Développez le nœud Lync Server 2010 pour afficher les différents rôles serveur dans le déploiement.

5.  Sélectionnez le nœud du site et vérifiez si l’option **Attribution de l’itinéraire de fédération du site** est définie.
    
    ![Générateur de topologies, itinéraire de Fédération du site](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Générateur de topologies, itinéraire de Fédération du site")

6.  Sélectionnez ensuite le serveur Standard Edition ou le pool frontal Enterprise Edition. Vérifiez si un pool Edge a été configuré pour les médias sous **Associations**.
    
    ![Générateur de topologies affichant les serveurs et les pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Générateur de topologies affichant les serveurs et les pools")

7.  Enfin, sélectionnez le pool Edge et vérifiez si un pool de tronçon suivant est configuré sous **Sélection du tronçon suivant**.
    
    ![Générateur de topologies, sélection du tronçon suivant](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Générateur de topologies, sélection du tronçon suivant")

**Vérifiez la configuration de partenaire fédéré XMPP héritée**

1.  À partir du serveur XMPP hérité, accédez à l’application\\outils d’administration Services.

2.  Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.
    
    ![Service de passerelle XMPP Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle XMPP Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

