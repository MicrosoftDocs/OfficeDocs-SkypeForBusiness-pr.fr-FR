---
title: 'Lync Server 2013 : Test du serveur Standard Edition'
TOCTitle: Test du serveur Standard Edition
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412890(v=OCS.15)
ms:contentKeyID: 49298622
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test du serveur Standard Edition dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

La procédure suivante explique comment tester le déploiement d’un serveur Standard Edition.

## Pour tester le déploiement d’un serveur Standard Edition

1.  Utilisez des ordinateurs et des utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle d’administrateur pour le déploiement Lync Server 2013 (sur lequel le Panneau de configuration Lync Server est installé) au groupe **CSAdministrator**.

2.  Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]  
    > Le compte d’utilisateur ne peut pas être l’administrateur local du serveur exécutant Lync Server 2013 Standard Edition. Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CSAdministrator, vous recevez une erreur lors de l’ouverture du Panneau de configuration Lync Server 2013, indiquant « Non autorisé : accès refusé en raison de l’échec de l’autorisation RBAC (contrôle d’accès basé sur un rôle) ».

3.  Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le Panneau de configuration Lync Server est installé.

4.  Démarrez le Panneau de configuration Lync Server et fournissez les informations d’authentification, si vous y êtes invité. Le Panneau de configuration Lync Server 2013 affiche les informations sur le déploiement.

5.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis confirmez que le statut du service est une icône d’ordinateur avec une flèche verte et qu’une coche verte figure en regard de chaque rôle de serveur Lync Server déployé et mis en ligne.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis activez les deux utilisateurs pour Lync Server 2013.

7.  Connectez un utilisateur sur un ordinateur lié au domaine et l’autre utilisateur sur un autre ordinateur du domaine.

8.  Installez Lync Server 2013 sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent ouvrir une session sur Lync Server 2013 et peuvent s’envoyer des messages instantanés entre eux.

## Voir aussi

#### Concepts

[Déploiement des clients et appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

