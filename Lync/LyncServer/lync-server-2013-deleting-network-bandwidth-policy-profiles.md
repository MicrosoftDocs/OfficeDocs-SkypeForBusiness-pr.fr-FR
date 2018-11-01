---
title: Suppression des profils de stratégie de bande passante réseau
TOCTitle: Suppression des profils de stratégie de bande passante réseau
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49891343
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des profils de stratégie de bande passante réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

La stratégie de bande passante utilisée dans le cadre du service Contrôle d’admission des appels permet de définir des restrictions de bande passante pour des modes bien précis. Dans Microsoft Lync Server 2013, seuls les modes audio et vidéo peuvent être soumis à des restrictions en matière de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de configuration Lync Server pour créer, modifier ou supprimer un profil conteneur pour ces stratégies. Utilisez les procédures suivantes pour supprimer des profils de stratégies de bande passante réseau. Pour plus d’informations sur la création ou la modification d’un profil de stratégie de bande passante réseau, voir [Création ou modification des profils de stratégie de bande passante](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

## Pour supprimer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs profils à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs profils. Pour sélectionner tous les profils, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.
    
    > [!WARNING]  
    > Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau. Vous devez d’abord supprimer l’association au site réseau avant de supprimer le profil. Pour plus d’informations sur la modification du site réseau, voir <a href="lync-server-2013-creating-or-modifying-network-sites.md">Création ou modification des sites réseau</a>.

## Voir aussi

#### Tâches

[Création ou modification des profils de stratégie de bande passante](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Affichage des informations d’un profil de stratégie de bande passante réseau](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  

#### Autres ressources

[Configuration du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

