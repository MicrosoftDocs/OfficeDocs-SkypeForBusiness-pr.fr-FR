---
title: Création ou modification des sites réseau
TOCTitle: Création ou modification des sites réseau
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520975(v=OCS.15)
ms:contentKeyID: 49296838
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des sites réseau

 

_**Dernière rubrique modifiée :** 2012-10-08_

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Le Panneau de configuration Microsoft Lync Server 2013 permet de configurer les sites et de les associer aux régions. Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site. Le Panneau de configuration Lync Server vous permet de créer, modifier ou supprimer des sites réseau. Utilisez les procédures suivantes pour créer ou modifier un site réseau. Pour plus d’informations sur la suppression d’un site réseau existant, voir [Suppression d’un site réseau existant](lync-server-2013-deleting-an-existing-network-site.md).

## Pour créer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur **Nouveau**.

5.  Dans **Nouveau site**, renseignez le champ **Nom**.
    
    > [!NOTE]  
    > Les noms de site doivent être uniques dans le déploiement Lync Server 2013.

6.  Dans la liste déroulante **Région**, sélectionnez une région réseau à associer au site.

7.  (Facultatif) Si vous voulez imposer sur ce site des limitations de bande passante aux appels audio ou vidéo, sélectionnez le profil de stratégie de bande passante adéquat dans la liste déroulante **Stratégie de bande passante**.
    
    > [!NOTE]  
    > Vous pouvez afficher les détails des profils de stratégie de bande passante ou créer un profil dans la page <strong>Profil de stratégie</strong> du groupe <strong>Configuration du réseau</strong>. Pour plus d’informations, voir <a href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Création ou modification des profils de stratégie de bande passante</a>.

8.  (Facultatif) Si vous voulez spécifier des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement**.
    
    > [!NOTE]  
    > La stratégie d’emplacement affecte les paramètres Enhanced 9-1-1 (E9-1-1) et d’emplacement des clients au site. Vous pouvez afficher les détails des stratégies d’emplacement ou créer une stratégie d’emplacement dans la page <strong>Stratégie d’emplacement</strong> du groupe <strong>Configuration du réseau</strong>. Pour plus d’informations, voir <a href="lync-server-2013-viewing-location-policy-information.md">Affichage des informations d’une stratégie d’emplacement</a>.

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site, car son nom ne suffit pas à le décrire.

10. Cliquez sur **Valider**.
    
    > [!NOTE]  
    > Lors de la création d’un site réseau, vous n’utilisez pas la table <strong>Sous-réseaux associés</strong>. Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau. Pour plus d’informations, voir <a href="lync-server-2013-create-or-modify-network-subnets.md">Création ou modification de sous-réseaux</a>.

## Pour modifier un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le site**, vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associés au site. Pour plus d’informations, voir « Pour créer un site réseau » plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier la table **Sous-réseaux associés** de cette page. La liste de sous-réseaux associés est donnée à titre de référence de sorte que vous sachiez quels sous-réseaux seront affectés par les paramètres que vous modifiez.

## Pour supprimer un site réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Site**.

4.  Dans la page **Site**, cliquez sur le site que vous souhaitez supprimer.
    
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs sites. Ou, pour sélectionner tous les sites, cliquez sur <strong>Sélectionner tout</strong> dans le menu <strong>Edition</strong>.

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    > [!WARNING]  
    > Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau de réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur <strong>Afficher les détails</strong> dans le menu <strong>Edition</strong>.

## Voir aussi

#### Tâches

[Suppression d’un site réseau existant](lync-server-2013-deleting-an-existing-network-site.md)  

#### Autres ressources

[New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

