---
title: 'Lync Server 2013 : Test du déploiement du pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Test du déploiement du pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-25_

La procédure suivante vous explique comment tester le déploiement du pool frontal.

<div>

## <a name="to-test-the-pool-deployment"></a>Pour tester le déploiement du pool

1.  Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur pour le déploiement de Lync Server 2013 (sur lequel est installé le panneau de configuration Lync Server 2013) vers le groupe **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous recevez un message d’erreur lors de l’ouverture du panneau de configuration de Lync Server, qui indique que l’accès à un contrôle de contrôle d’accès basé sur les rôles (RBAC) est refusé en raison d’un échec de l’autorisation de contrôle d’accès basé sur un rôle.»

    
    </div>

2.  Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    <div>
    

    > [!NOTE]  
    > Le compte d’utilisateur ne peut pas être l’administrateur local de tout serveur exécutant Lync Server 2013.

    
    </div>

3.  Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le panneau de configuration de Lync Server est installé.

4.  Démarrez le panneau de configuration de Lync Server, puis fournissez les informations d’identification, le cas échéant. Le panneau de configuration de Lync Server affiche des informations de déploiement.

5.  Dans la barre de navigation de gauche, cliquez sur **Topology**, puis vérifiez que l’état du service affiche un ordinateur avec une flèche verte et qu’une coche verte pour l’état de réplication est située en regard de chaque rôle serveur Lync Server déployé et remis en ligne.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.

7.  Dans la page **nouveau serveur Lync** , cliquez sur **Ajouter**.

8.  Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Après avoir choisi les options de recherche, **sélectionnez Rechercher**.

9.  Dans le volet résultats de la recherche, sélectionnez tous les objets pour cette session de recherche, puis cliquez sur **OK**.

10. Dans la page **nouvel utilisateur de Lync Server** , le ou les objets que vous avez sélectionnés apparaissent dans l’affichage **utilisateurs** . Dans la liste **attribuer des utilisateurs à un pool** , sélectionnez le serveur sur lequel les objets doivent être hébergés.
    
    Vous trouverez ci-dessous un certain nombre d’options de configuration des objets.
    
      - **Générer l’URL SIP de l’utilisateur**
    
      - **Téléphonie**
    
      - **URI de ligne**
    
      - **Stratégie de conférence**
    
      - **Stratégie de version du client**
    
      - **Stratégie de code confidentiel**
    
      - **Stratégie d’accès externe**
    
      - **Stratégie d’archivage**
    
      - **Stratégie d’emplacement**
    
      - **Stratégie du client**
    
    Pour tester la fonctionnalité de base, sélectionnez l’option de votre choix pour le paramètre **URI SIP de l’utilisateur générer** (les autres options dans la configuration utiliseront les paramètres par défaut), puis cliquez sur **activer**.

11. Une page de résumé s’ouvre et affiche une coche dans la colonne **activé** pour indiquer que les objets sont désormais prêts à l’emploi. La colonne **adresse SIP** affiche l’adresse dont vous avez besoin pour la configuration de connexion de l’utilisateur.

12. Connectez un utilisateur à un ordinateur joint au domaine et un autre utilisateur à un autre ordinateur du domaine.

13. Installez Lync 2013 sur chacun des deux ordinateurs client, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et pouvoir vous envoyer des messages instantanés.

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

