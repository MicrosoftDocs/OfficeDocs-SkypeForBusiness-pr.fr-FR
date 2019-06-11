---
title: 'Lync Server 2013 : Test du serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Test du serveur Standard Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

La procédure suivante vous explique comment tester le déploiement d’un serveur Standard Edition Server.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Pour tester le déploiement d’un serveur Standard Edition Server

1.  Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Lync Server 2013 (sur lequel est installé le panneau de configuration Lync Server) vers le groupe **CSAdministrator** .

2.  Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    <div>
    

    > [!NOTE]  
    > Le compte d’utilisateur ne peut pas être l’administrateur local du serveur exécutant Lync Server 2013 Standard Edition. Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration de Lync Server 2013, qui indique que l’accès non autorisé est refusé en raison d’un échec d’autorisation de contrôle d’accès basé sur un rôle (RBAC).»

    
    </div>

3.  Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le panneau de configuration de Lync Server est installé.

4.  Démarrez le panneau de configuration de Lync Server et fournissez les informations d’identification, le cas échéant. Le panneau de configuration de Lync Server 2013 affiche des informations de déploiement.

5.  Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service est une icône d’ordinateur avec une flèche verte et qu’une coche verte apparaît à côté de chaque rôle serveur Lync Server déployé et remis en ligne.

6.  Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis activez les deux utilisateurs pour Lync Server 2013.

7.  Connectez un utilisateur à un ordinateur joint au domaine et à l’autre utilisateur sur un autre ordinateur du domaine.

8.  Installez Lync Server 2013 sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et pouvoir vous envoyer des messages instantanés.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

