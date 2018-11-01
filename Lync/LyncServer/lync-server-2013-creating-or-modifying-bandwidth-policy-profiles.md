---
title: Création ou modification des profils de stratégie de bande passante
TOCTitle: Création ou modification des profils de stratégie de bande passante
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520945(v=OCS.15)
ms:contentKeyID: 49296176
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des profils de stratégie de bande passante

 

_**Dernière rubrique modifiée :** 2012-10-15_

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Microsoft Lync Server 2013, seuls les modes audio et vidéo peuvent être soumis à des restrictions en matière de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de configuration Lync Server pour créer, modifier ou supprimer un profil pour ces stratégies au sein du conteneur. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Effectuez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante. Pour supprimer un profil de stratégie de bande passante, voir [Suppression des profils de stratégie de bande passante réseau](lync-server-2013-deleting-network-bandwidth-policy-profiles.md).

## Pour créer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante**, cliquez sur **Nouveau**.

5.  Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **Nom**. Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **Limite audio**, tapez une valeur numérique. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions audio.

7.  Entrez une valeur numérique dans le champ **Limite de session audio**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion audio. Cette valeur doit être égale ou supérieure à 40.

8.  Entrez une valeur numérique dans le champ **Limite vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions vidéo.

9.  Entrez une valeur numérique dans le champ **Limite de session vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion vidéo. Cette valeur doit être égale ou supérieure à 100.

10. (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante, car son nom ne suffit pas à le décrire.

11. Cliquez sur **Valider**.
    
    > [!NOTE]  
    > La création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de stratégie à un site. Pour plus d’informations sur la procédure pour associer un profil de stratégie à un site, voir <a href="lync-server-2013-creating-or-modifying-network-sites.md">Création ou modification des sites réseau</a>.

## Pour modifier un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le profil de stratégie de bande passante**, modifiez les champs comme il convient (pour plus d’informations, voir la section « Pour créer un profil de stratégie de bande passante » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.
    
    > [!NOTE]  
    > Lorsque vous modifiez le profil de stratégie de bande passante, celui-ci met immédiatement à jour les restrictions de bande passante de tous les sites réseau qui lui sont associés.

## Voir aussi

#### Tâches

[Suppression des profils de stratégie de bande passante réseau](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Autres ressources

[Configuration du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

