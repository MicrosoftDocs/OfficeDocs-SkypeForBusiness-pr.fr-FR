---
title: Création ou modification des itinéraires de région réseau
TOCTitle: Création ou modification des itinéraires de région réseau
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521016(v=OCS.15)
ms:contentKeyID: 49297759
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des itinéraires de région réseau

 

_**Dernière rubrique modifiée :** 2012-10-08_

Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions. Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre. Vous pouvez utiliser le Panneau de configuration Lync Server pour configurer les itinéraires de région réseau. Le Panneau de configuration Lync Server vous permet de créer, de modifier ou de supprimer un itinéraire de région réseau. Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau. Pour plus d’informations sur la suppression d’itinéraires de région réseau existants, voir [Suppression des itinéraires de zones réseau existants](lync-server-2013-deleting-existing-network-region-routes.md).

## Pour créer un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur **Nouveau**.

5.  Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **Nom**.
    
    > [!NOTE]  
    > Cette valeur doit être unique dans votre déploiement Microsoft Lync Server 2013.

6.  Dans la liste déroulante **Région réseau n° 1**, sélectionnez l’une des deux régions à connecter par cet itinéraire.

7.  Dans la liste déroulante **Région réseau n° 2**, sélectionnez l’autre région pour cet itinéraire. Cette région doit être différente de la région sélectionnée pour Région réseau n° 1.

8.  Utilisez la zone de liste **Liens de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région**. Cliquez sur un lien de région pour l’ajouter à cet itinéraire, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Continuez à cliquer sur le bouton <strong>Ajouter</strong> pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur <strong>Supprimer</strong> pour le supprimer.

9.  Cliquez sur **Valider**.

## Pour modifier un itinéraire de région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.

4.  Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans **Modifier l’itinéraire de région**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région qui lui sont associés.

7.  Cliquez sur **Valider**.

## Voir aussi

#### Tâches

[Suppression des itinéraires de zones réseau existants](lync-server-2013-deleting-existing-network-region-routes.md)

