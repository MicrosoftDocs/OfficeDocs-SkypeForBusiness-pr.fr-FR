---
title: "Lync Server 2013 : Conf. des param. de réach. de la messagerie vocale"
TOCTitle: Configuration des paramètres de réacheminement de la messagerie vocale
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398606(v=OCS.15)
ms:contentKeyID: 49297817
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des paramètres de réacheminement de la messagerie vocale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-18_

Les serveurs Survivable Branch Appliance et serveurs Survivable Branch Server permettent de fournir la survivabilité de la messagerie vocale en cas de panne du réseau étendu (WAN), si la messagerie unifiée Exchange est installée sur le site central et qu’un standard automatique de messagerie unifiée Exchange est déployé. Nous conseillons que votre administrateur Exchange configure le standard automatique de manière à accepter uniquement les messages, ce qui désactive d’autres fonctionnalités génériques telles que le transfert vers un utilisateur ou un opérateur. Vous pouvez également utiliser un standard automatique générique ou personnaliser pour acheminer l’appel.

Pour plus d’informations, reportez-vous à la section « Préparation à la survivabilité de la messagerie vocale » de [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) dans la documentation de planification.

## Pour configurer la survivabilité de la messagerie vocale

1.  Demandez à votre administrateur Exchange de configurer le standard automatique de manière à accepter uniquement les messages (utilisez l’applet de commande suivante dans Exchange Shell : **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**). Le paramètre qui spécifie de laisser des messages ( *SendVoiceMsgEnabled*) a la valeur True par défaut.

2.  Dans Lync Server Management Shell, utilisez l’applet de commande **New-CSVoiceMailReroutingConfiguration** pour définir le numéro de téléphone du standard automatique comme numéro de téléphone de standard automatique de la messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
    > [!NOTE]  
    > Si vous avez besoin de modifier le paramètre de réacheminement de la messagerie vocale ultérieurement, utilisez pour cela l’applet de commande <strong>Set-CsVoiceMailReRoutingConfiguration</strong>. Pour plus d’informations sur <strong>New-</strong> et <strong>Set-CSVoiceMailReroutingConfiguration</strong>, reportez-vous aux rubriques d’aide du Shell.

3.  Configurez le numéro d’accès d’abonné à la messagerie unifiée Exchange qui correspond au plan de numérotation de messagerie unifiée Exchange de l’utilisateur de succursale comme numéro d’accès d’abonné à la messagerie unifiée Exchange dans la configuration de réacheminement de la messagerie vocale sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
    > [!NOTE]  
    > Configurez le plan de numérotation de messagerie unifiée Exchange de l’utilisateur afin qu’il n’y ait qu’un seul plan de numérotation associé à tous les utilisateurs de succursale ayant besoin d’accéder à la fonctionnalité Obtenir la messagerie vocale pendant une panne du réseau étendu (WAN).

**Étape suivante** pour les serveurs Survivable Branch Appliance ou les serveurs Survivable Branch Server : [Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

