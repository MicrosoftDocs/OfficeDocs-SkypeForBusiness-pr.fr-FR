---
title: "Lync Server 2013 : Créa. ou modification des fournisseurs fédérés SIP hébergés"
TOCTitle: Création ou modification des fournisseurs fédérés SIP hébergés
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ552445(v=OCS.15)
ms:contentKeyID: 49296249
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des fournisseurs fédérés SIP hébergés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

La connectivité de messagerie instantanée de fournisseur hébergé permet aux utilisateurs de votre organisation de recourir à la messagerie instantanée pour communiquer avec des utilisateurs de services de messagerie instantanée fournis par des fournisseurs hébergés, notamment à l’aide de Microsoft Office 365 et de Lync Online.

Chaque fournisseur hébergé est configuré avec le nom de domaine complet du serveur Edge du fournisseur et le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** .

Procédez comme suit pour créer ou modifier des fournisseurs hébergés :

## Pour créer ou modifier des fournisseurs hébergés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe** , puis sur **Fournisseurs fédérés SIP** .

4.  Si vous devez créer un nouveau fournisseur hébergé, cliquez sur **Nouveau** , puis sur **Fournisseur hébergé** .

5.  Si vous devez modifier une entrée dans la liste des fournisseurs hébergés, sélectionnez un fournisseur hébergé, cliquez sur **Modifier** , puis sur **Afficher les détails** .

6.  Dans la page **Modifier le fournisseur fédéré SIP** , vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur** Ce paramètre active les communications avec les utilisateurs de ce fournisseur.
    
      - **Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il s’affichera dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :** propriété requise. Tapez le nom de domaine complet du service Edge d’accès du fournisseur hébergé que vous configurez. Cette information doit être fournie par le fournisseur hébergée et ne doit être modifiée que si le fournisseur hébergé modifie le nom de domaine complet de son service Edge d’accès.
    
      - **Niveau de vérification par défaut :** le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.
        
        Sélectionnez **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** pour supprimer la restriction sur la réception et l’acceptation d’invitations de contacts. Ce paramètre n’applique aucune restriction sur les personnes qui peuvent vous contacter à partir du réseau du fournisseur hébergé.

7.  Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.

## Voir aussi

#### Tâches

[Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

