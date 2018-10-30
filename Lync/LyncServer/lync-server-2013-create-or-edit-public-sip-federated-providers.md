---
title: "Lync Server 2013 : Créa. ou modification des fournisseurs fédérés SIP publics"
TOCTitle: Création ou modification des fournisseurs fédérés SIP publics
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398349(v=OCS.15)
ms:contentKeyID: 49297237
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée publics, notamment Windows Live Messenger, Yahoo\! et AOL.

Lync Server 2013 dispose de configurations de fournisseurs publics pour la messagerie instantanée America Online, Windows Live et Yahoo\!. Chaque fournisseur public est configuré à l’aide du nom de domaine complet du serveur Edge du fournisseur et avec le niveau de vérification par défaut **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur**.

Par défaut, aucun des fournisseurs publics n’est activé. Terminez le travail relatif au contrat de licence et à l’approvisionnement avant d’activer les fournisseurs publics. Vous pouvez activer le fournisseur avant de terminer le travail relatif au contrat de licence et à l’approvisionnement. Les utilisateurs ne pourront pas communiquer avec leurs contacts situés chez ces fournisseurs tant que le travail préalable ne sera pas terminé. Pour plus d’informations sur les licences et l’approvisionnement des fournisseurs publics, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Procédez comme suit pour créer ou modifier des fournisseurs publics :

## Pour créer ou modifier des fournisseurs publics

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Fournisseurs fédérés SIP**.

4.  Pour créer un fournisseur public, cliquez sur **Nouveau**, puis sur **Fournisseur public**.

5.  Si vous devez modifier une entrée dans la liste des fournisseurs publics, sélectionnez un fournisseur public, cliquez sur **Modifier**, puis sur **Afficher les détails**.

6.  Dans la page **Modifier le fournisseur fédéré SIP**, vous pouvez taper ou modifier les paramètres suivants :
    
      - **Activer les communications avec ce fournisseur**    La sélection de ce paramètre permet aux utilisateurs de ce fournisseur d’accéder à la messagerie instantanée.
    
      - **Nom du fournisseur :** propriété requise. Tapez le nom du fournisseur tel qu’il s’affichera dans la liste des fournisseurs fédérés SIP.
    
      - **Service Edge d’accès (FQDN) :** propriété requise. Tapez le nom de domaine complet du service Edge d’accès du fournisseur que vous configurez. Ces informations sont fournies par défaut et ne doivent être changées que si le fournisseur public modifie le nom de domaine complet du service Edge d’accès au niveau du fournisseur public.
    
      - **Niveau de vérification par défaut :** le paramètre par défaut, **Autoriser les utilisateurs à communiquer avec les personnes dans leur liste des contacts qui utilisent ce fournisseur** limite la communication aux contacts que vous avez acceptés et qui figurent dans votre liste des contacts.
        
        La sélection du paramètre **Autoriser les utilisateurs à communiquer avec toutes les personnes qui utilisent ce fournisseur** supprime la restriction que vous devez avoir reçue et permet d’accepter l’invitation d’un contact. Ce paramètre n’impose pas de limite aux personnes qui peuvent vous contacter à partir du réseau du fournisseur public.

7.  Quand vous avez terminé de configurer les paramètres, cliquez sur **Valider** pour les enregistrer ou sur **Annuler** pour annuler vos modifications.

## Voir aussi

#### Tâches

[Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

