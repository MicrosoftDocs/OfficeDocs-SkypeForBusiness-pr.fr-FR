---
title: Modification des paramètres de configuration d’un service web existant
TOCTitle: Modification des paramètres de configuration d’un service web existant
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182580(v=OCS.15)
ms:contentKeyID: 49298681
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des paramètres de configuration d’un service web existant

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez utiliser la page **Service web** pour configurer les méthodes d’authentification permettant d’accéder aux serveurs et services web Lync Server 2013.

Procédez comme suit pour modifier une stratégie de service web existante.

## Pour modifier un service web existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.

4.  Dans la page **Service web**, cliquez successivement sur une configuration, sur le menu **Edition**, puis sur **Afficher les détails**.

5.  Dans **Modifier le paramètre de service web**, sous **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucune**.

6.  Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
      - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
      - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.

7.  Cliquez sur **Valider**.

## Voir aussi

#### Autres ressources

[Configuration de la sécurité](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

