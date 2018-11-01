---
title: Affichage des informations d’un profil de stratégie de bande passante réseau
TOCTitle: Affichage des informations d’un profil de stratégie de bande passante réseau
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49891603
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’un profil de stratégie de bande passante réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée afin de définir les restrictions de bande passantes pour certains modes. Dans Microsoft Lync Server 2013, seuls les modes audio et vidéo peuvent être soumis à des restrictions en matière de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le Panneau de configuration Lync Server pour créer, modifier ou supprimer un profil pour ces stratégies au sein du conteneur. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Suivez les procédures ci-dessous pour voir un profil de stratégie de bande passante. Pour créer ou modifier un profil de stratégie de bande passante, voir [Création ou modification des profils de stratégie de bande passante](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md) (contenu éventuellement en anglais).

## Pour modifier un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Sur la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

## Affichage des informations de profil de stratégie de bande passante de réseau à l’aide des cmdlets Lync Server PowerShell

Les profils de bande passante de réseau peuvent aussi être affichés à l’aide de Lync Server PowerShell et de la cmdlet Get-CsNetworkBandwidthPolicyProfile. Celle-ci peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affichage des informations de profil de stratégie de bande passante réseau

  - Pour voir les informations relatives à tous vos profils de stratégie de bande passante réseau, tapez la commande suivante dans Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

Pour plus d’informations, voir la rubrique d’aide pour la cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) (contenu éventuellement en anglais).

## Voir aussi

#### Tâches

[Création ou modification des profils de stratégie de bande passante](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Suppression des profils de stratégie de bande passante réseau](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Autres ressources

[Configuration du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)

