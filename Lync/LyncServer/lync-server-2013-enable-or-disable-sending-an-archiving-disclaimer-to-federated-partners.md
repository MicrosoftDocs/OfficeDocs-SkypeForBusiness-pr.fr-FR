---
title: "LS 2013 : Act. ou dés. envoi notif. d’excl. rel. à l’arch. aux parten. féd."
TOCTitle: Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182584(v=OCS.15)
ms:contentKeyID: 49298841
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la notification d’exclusion relative à l’archivage doit être automatiquement envoyée aux partenaires fédérés. Si vous archivez des communications externes, vous devez activer l’envoi d’une notification d’exclusion relative à l’archivage. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise. Pour plus d’informations sur l’activation de la fédération, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a> dans la documentation relative au déploiement ou aux opérations.

## Pour activer ou désactiver l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Sous l’onglet **Configuration du serveur Edge d’accès**, cliquez sur **Global**, **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, sous **Autoriser les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** pour activer ou désactiver l’envoi automatique d’une notification d’exclusion relative à l’archivage.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec les utilisateurs dans votre déploiement Lync Server 2013, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) dans la documentation de déploiement ou des opérations. Pour plus d’informations sur le contrôle d’accès de domaines fédérés spécifiques, reportez-vous à [Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation de déploiement ou des opérations.

## Activation et désactivation de la notification d’exclusion relative à l’archivage à l’aide des applets de commande Windows PowerShell

L’utilisation de la notification d’exclusion relative à l’archivage peut également être gérée via Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).)

## Activer la notification d’exclusion relative à l’archivage

  - Pour activer la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## Désactiver la notification d’exclusion relative à l’archivage

  - Pour désactiver la notification d’exclusion relative à l’archivage, définissez la valeur de la propriété **EnableArchivingDisclaimer** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

