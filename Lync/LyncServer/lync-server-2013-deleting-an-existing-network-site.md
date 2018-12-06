---
title: Suppression d’un site réseau existant
TOCTitle: Suppression d’un site réseau existant
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49891274
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un site réseau existant

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1. Le Panneau de configuration Lync Server 2013 permet de configurer les sites et de les associer aux régions. Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver. Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site. Le Panneau de configuration Lync Server vous permet de créer, modifier ou supprimer des sites réseau. Utilisez la procédure suivante pour supprimer un site réseau existant. Pour plus d’informations sur la création et la modification des sites réseau, voir [Création ou modification des sites réseau](lync-server-2013-creating-or-modifying-network-sites.md).

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
    > Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur <strong>Afficher les détails</strong> dans le menu <strong>Edition</strong>.
