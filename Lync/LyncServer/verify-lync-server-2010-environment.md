---
title: Vérification de l’environnement Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Vérification de l’environnement Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Avant de déployer Lync Server 2013 dans un état de coexistence avec Lync Server 2010, vous devez vérifier que les services Lync Server 2010 ont été configurés et démarrés. Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool de pilotes 2013 Lync Server. Avant de déployer Microsoft Lync Server 2013 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée. La vérification de votre déploiement hérité de Lync Server 2010 implique les éléments suivants:

  - Vérification du démarrage des services 2010 de Lync Server

  - Examen de la topologie et des utilisateurs dans Lync Server 2010.

  - Vérification des paramètres de serveur de Fédération et de périmètre.

  - Vérification des services XMPP et des partenaires fédérés.

**Vérifier le démarrage des services Lync Server 2010**

1.  À partir du serveur frontal Lync Server 2010, accédez à l’applet\\services d’administration.

2.  Vérifiez que les services suivants s’exécutent sur le serveur frontal:
    
    ![Liste des services s’exécutant sur un serveur frontal] (images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste des services s’exécutant sur un serveur frontal")

**Passez en revue la topologie Lync Server 2010 dans le panneau de configuration de Lync Server**

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le panneau de configuration de Lync Server.

3.  Sélectionnez **topologie**. Vérifiez que les différents serveurs de votre déploiement de Lync Server 2010 sont répertoriés.
    
    ![Page Topology du panneau de configuration de Lync Server 2010] (images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Page Topology du panneau de configuration de Lync Server 2010")

**Pour passer en revue les utilisateurs de Lync Server 2010 dans le panneau de configuration de Lync Server**

1.  Ouvrez le panneau de configuration de Lync Server.

2.  Sélectionnez **utilisateurs** , puis cliquez sur **Rechercher**.

3.  Vérifiez que la colonne **pool d’inscriptions** pointe vers le pool Lync Server 2010 pour chaque utilisateur répertorié.
    
    ![Lync Server 2010-panneau de configuration avec liste des utilisateurs] (images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010-panneau de configuration avec liste des utilisateurs")

**Pour vérifier les paramètres de périphérie et de Fédération de Lync Server 2010**

1.  Démarrer le générateur de topologie.

2.  Sélectionnez **Télécharger la topologie à partir du déploiement existant**.

3.  Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.

4.  Développez le nœud Lync Server 2010 pour révéler les différents rôles de serveur du déploiement.

5.  Sélectionnez le nœud site et vérifiez qu’une valeur d' **attribution d’itinéraire de Fédération de site** est définie.
    
    ![Générateur de topologie, itinéraire de Fédération de site] (images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Générateur de topologie, itinéraire de Fédération de site")

6.  Sélectionnez ensuite le pool frontal Standard Edition Server ou Enterprise Edition. Déterminez si un pool de périphérie a été configuré pour **** les médias suivants.
    
    ![Générateur de topologie affichant des serveurs et des groupes] (images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Générateur de topologie affichant des serveurs et des groupes")

7.  Enfin, sélectionnez le pool de bords et déterminez si un pool de prochains tronçons est configuré en dessous de la **sélection du tronçon suivant**.
    
    ![Générateur de topologie, sélection du tronçon suivant] (images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Générateur de topologie, sélection du tronçon suivant")

**Vérification de la configuration de partenaire fédéré hérité de XMPP**

1.  À partir du serveur XMPP hérité, accédez à l’applet\\services des outils d’administration.

2.  Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré.
    
    ![Service de passerelle Office Communications Server XMPP] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle Office Communications Server XMPP")

</div>

<span> </span>

</div>

</div>

</div>

