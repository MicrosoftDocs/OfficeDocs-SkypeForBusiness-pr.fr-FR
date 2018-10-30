---
title: 'Lync Server 2013 : Test du déploiement du pool'
TOCTitle: Test du déploiement du pool
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413092(v=OCS.15)
ms:contentKeyID: 49299464
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test du déploiement du pool dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-09-25_

La procédure suivante explique comment tester le déploiement du pool de serveurs frontaux.

## Pour tester le déploiement du pool

1.  Utilisez Ordinateurs et utilisateurs Active Directory pour ajouter l’objet utilisateur Active Directory du rôle administrateur du déploiement Lync Server 2013 (où Panneau de configuration Lync Server 2013 est installé) au groupe **CSAdministrator**.
    
    > [!IMPORTANT]  
    > Si vous n’ajoutez pas les utilisateurs et les groupes appropriés au groupe CsAdministors, vous obtiendrez un message d’erreur lors de l’ouverture du Panneau de configuration Lync Server, indiquant « Non autorisé : l’accès est refusé en raison d’un échec d’autorisation du contrôle d’accès basé sur un rôle (RBAC) ».

2.  Si l’objet utilisateur est actuellement connecté, fermez, puis rouvrez la session pour inscrire la nouvelle affectation de groupe.
    
    > [!NOTE]  
    > Le compte d’utilisateur ne peut pas être l’administrateur local d’un serveur exécutant Lync Server 2013.

3.  Utilisez le compte administratif pour vous connecter à l’ordinateur sur lequel le Panneau de configuration Lync Server est installé.

4.  Démarrez le Panneau de configuration Lync Server, puis fournissez les informations d’identification, si vous y êtes invité. Le Panneau de configuration Lync Server affiche les informations sur le déploiement.

5.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis confirmez que le statut du service montre un ordinateur avec une flèche verte et qu’une coche verte pour le statut de réplication se trouve en regard de chaque rôle serveur Lync Server déployé et mis en ligne.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Activer les utilisateurs**.

7.  Dans la page **Nouvel utilisateur Lync Server**, cliquez sur **Ajouter**.

8.  Pour définir les paramètres de recherche des objets que vous souhaitez trouver, sur la page **Sélectionner à partir d’Active Directory**, vous pouvez sélectionner **Rechercher**, puis éventuellement cliquer sur **Ajouter un filtre**. Vous pouvez également sélectionner **Recherche LDAP** et entrer une expression LDAP pour filtrer ou limiter les objets qui seront renvoyés. Une fois que vous avez défini vos options de recherche, cliquez sur **Rechercher**.

9.  Dans le volet de résultats, sélectionnez tous les objets de cette session de recherche, puis cliquez sur **OK**.

10. Dans la page **Nouvel utilisateur Lync Server**, le ou les objets sélectionnés se trouvent dans l’affichage **Utilisateurs**. Dans la liste **Attribuer des utilisateurs à un pool**, sélectionnez le serveur qui devrait héberger les objets.
    
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

12. Connectez un utilisateur sur un ordinateur lié au domaine et un autre utilisateur sur un autre ordinateur du domaine.

13. Installez Lync 2013 sur chacun des deux ordinateurs clients, puis vérifiez que les deux utilisateurs peuvent ouvrir une session sur Lync Server 2013 et peuvent s’envoyer des messages instantanés entre eux.

## Voir aussi

#### Concepts

[Déploiement des clients et appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

