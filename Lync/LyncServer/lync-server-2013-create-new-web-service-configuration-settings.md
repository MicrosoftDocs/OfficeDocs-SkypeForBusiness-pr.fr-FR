---
title: Création des paramètres de configuration d’un service web
TOCTitle: Création des paramètres de configuration d’un service web
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182605(v=OCS.15)
ms:contentKeyID: 49299319
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création des paramètres de configuration d’un service web

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez utiliser la page **Service Web** pour configurer les méthodes d’authentification permettant d’accéder aux serveurs et services Web Lync Server 2013.

Procédez comme suit pour créer une stratégie de service Web.

## Pour créer une stratégie de service Web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service Web**.

4.  Sur la page **Service Web**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour configurer le service Web pour un site, cliquez sur **Configuration du site**. Dans **Sélectionner un site**, cliquez sur le site auquel le service Web s’appliquera, puis cliquez sur **OK**.
    
      - Pour configurer le service Web pour un pool, cliquez sur **Configuration du pool**. Dans **Sélectionner un service**, cliquez sur le service auquel la stratégie de service Web s’appliquera, puis cliquez sur **OK**.

5.  Dans **Nouveau paramètre de service Web**, dans **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucun**.

6.  Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
      - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
      - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.

7.  Cliquez sur **Valider**.

