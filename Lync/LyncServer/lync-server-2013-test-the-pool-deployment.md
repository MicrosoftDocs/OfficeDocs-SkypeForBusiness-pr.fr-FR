---
title: 'Lync Server 2013 : test du déploiement du pool'
description: 'Lync Server 2013 : test du déploiement du pool.'
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
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576040"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Test du déploiement du pool dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-25_

La procédure suivante décrit comment tester le déploiement du pool frontal.

<div>

## <a name="to-test-the-pool-deployment"></a>Pour tester le déploiement du pool

1.  Utilisez les ordinateurs et les utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement de Lync Server 2013 (sur lequel le panneau de configuration Lync Server 2013 est installé) au groupe **CSAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous n’ajoutez pas les utilisateurs et groupes appropriés au groupe CsAdministors, vous recevrez un message d’erreur lors de l’ouverture du panneau de configuration Lync Server, qui indique que « l’accès est refusé en raison d’un échec d’autorisation de contrôle d’accès basé sur un rôle (RBAC) ».

    
    </div>

2.  Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    <div>
    

    > [!NOTE]  
    > Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Lync Server 2013.

    
    </div>

3.  Utilisez le compte d’administrateur pour vous connecter à l’ordinateur sur lequel le panneau de configuration Lync Server est installé.

4.  Démarrez le panneau de configuration Lync Server, puis fournissez les informations d’identification, si vous y êtes invité. Le panneau de configuration Lync Server affiche des informations sur le déploiement.

5.  Dans la barre de navigation de gauche, cliquez sur **topologie**, puis confirmez que l’état du service indique un ordinateur avec une flèche verte et qu’une coche verte pour l’état de réplication est en regard de chaque rôle serveur Lync Server déployé et mis en ligne.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.

7.  Sur la page **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.

8.  Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.

9.  Dans le volet de résultats, sélectionnez tous les objets de cette session de recherche, puis cliquez sur **OK**.

10. Sur la page **Nouvel utilisateur Lync Server**, le ou les objets sélectionnés se trouvent dans l’affichage **Utilisateurs**. Dans la liste **Attribuer des utilisateurs à un pool**, sélectionnez le serveur qui devrait héberger les objets.
    
    Ce qui suit est une série d’options pour configurer les objets.
    
      - **Générer l’URI SIP de l’utilisateur**
    
      - **Téléphonie**
    
      - **URI de ligne**
    
      - **Stratégie de conférence**
    
      - **Stratégie de version du client**
    
      - **Stratégie de code confidentiel**
    
      - **Stratégie d’accès externe**
    
      - **Stratégie d’archivage**
    
      - **Stratégie d’emplacement**
    
      - **Stratégie du client**
    
    Pour tester les fonctionnalités de base, sélectionnez votre option préférée pour le paramètre **Générer l’URI SIP de l’utilisateur** (les autres options de la configuration utiliseront les paramètres par défaut), puis cliquez sur **Activer**.

11. Une page récapitulative s’affiche. Elle contient une coche dans la colonne **Activé** pour indiquer que les objets sont désormais prêts à être utilisés. La colonne **Adresse SIP** affiche l’adresse dont vous avez besoin pour configurer la connexion de l’utilisateur.

12. Connectez un utilisateur sur un ordinateur qui est lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.

13. Installez Lync 2013 sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent se connecter à Lync Server 2013 et peuvent envoyer des messages instantanés.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement des clients et des périphériques dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

