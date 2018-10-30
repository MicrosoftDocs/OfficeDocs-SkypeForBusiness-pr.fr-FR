---
title: 'Lync Server 2013 : Définition d’une adresse IP de passerelle SIP/CSTA'
TOCTitle: Définition d’une adresse IP de passerelle SIP/CSTA
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg602125(v=OCS.15)
ms:contentKeyID: 49298545
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Si Lync Server doit se connecter à la passerelle SIP/CSTA déployée pour le contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez définir l’adresse IP de la passerelle dans le Générateur de topologie. Cette étape n’est pas nécessaire pour les passerelles qui prennent en charge les connexions TLS (Transport Layer Security). Pour ces passerelles, vous pouvez ignorer cette procédure et poursuivre le déploiement du contrôle d’appel distant en suivant les étapes décrites dans la section [Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

## Pour définir l’adresse IP de la passerelle SIP/CSTA à l’aide du générateur de topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

3.  Choisissez l’option consistant à télécharger une topologie existante.

4.  Développez le nœud **Serveurs d’applications approuvés** .

5.  Cliquez avec le bouton droit de la souris sur le pool d’applications approuvées que vous avez créé, comme indiqué dans la section [Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), puis cliquez sur **Modifier les propriétés** .

6.  Désactivez la case à cocher **Activer la réplication des données de configuration sur ce pool** .

7.  Cliquez sur **Limiter l’utilisation des services aux adresses IP sélectionnées** . Le paramètre par défaut est **Utiliser toutes les adresses IP configurées** .

8.  Dans la zone de texte **Adresse IP principale** , entrez l’adresse IP de la passerelle SIP/CSTA.

9.  Pour mettre à jour la topologie dans le magasin central de gestion, dans l’arborescence de la console, cliquez sur **Lync Server** , puis, dans le volet **Actions** , cliquez sur **Publier** .

## Voir aussi

#### Tâches

[Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

