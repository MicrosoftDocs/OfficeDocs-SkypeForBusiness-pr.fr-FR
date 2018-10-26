---
title: 'Lync Server 2013 : Test du directeur'
TOCTitle: Test du directeur
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398767(v=OCS.15)
ms:contentKeyID: 49298139
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test du directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

À ce stade, vous avez configuré un directeur et un pool directeur, mais vos entrées DNS SRV pointent toujours les clients vers une connexion utilisant un pool ou un serveur Standard Edition. Avant de modifier l’enregistrement DNS pour que les clients Lync 2013 se connectent automatiquement à l’aide du directeur, testez un client en le pointant manuellement sur le directeur.

## Pour tester le déploiement

1.  Ouvrez une session sur l’ordinateur sur lequel est installé le Panneau de configuration Lync Server avec un compte de domaine faisant partie du groupe **CSAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans le volet de navigation, cliquez sur **Topologie**, et dans la colonne **État**, confirmez la présence d’une marque en forme de flèche verte sur serveur (comme ceci, ![Icône de serveur avec flèche verte](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icône de serveur avec flèche verte")) pour votre directeur ou pool directeur.

4.  Connectez deux ordinateurs clients sur lesquels est installé Lync Server 2013 et ouvrez une session avec un autre compte d’utilisateur activé pour Lync Server 2013 sur chaque ordinateur.

5.  Sur l’un des ordinateurs clients, cliquez sur le menu **Options**, sélectionnez le groupe de paramètres **Personnel**, cliquez sur **Avancés**, sur **Configuration manuelle**, puis définissez le **Nom ou adresse IP du serveur interne** avec le nom de domaine complet du nouveau directeur ou pool directeur.

6.  Connectez-vous sur les deux clients et vérifiez que l’ouverture de session à l’aide du directeur fonctionne normalement, permet de visualiser le statut de présence de l’autre utilisateur et que les deux utilisateurs peuvent échanger des messages instantanés.

