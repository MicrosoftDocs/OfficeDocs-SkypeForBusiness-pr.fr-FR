---
title: "Lync Server 2013 : Act. ou dés. de la découverte de partenaires de fédération"
TOCTitle: Activation ou désactivation de la découverte de partenaires de fédération
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182550(v=OCS.15)
ms:contentKeyID: 49298078
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Lorsque vous déployez vos serveurs Edge et activez la fédération pour votre entreprise, vous devez spécifier si la découverte des domaines partenaires fédérés doit être prise en charge automatiquement. Utilisez la procédure de cette rubrique pour modifier cette configuration.

> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la fédération pour votre entreprise. Pour plus d’informations sur l’activation de la fédération, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a> dans la documentation relative au déploiement ou aux opérations.

## Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre entreprise

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes** , puis sur **Configuration du serveur Edge d’accès** .

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global** , sur **Modifier** , puis sur **Afficher les détails** .

5.  Dans **Modifier la configuration du serveur Edge d’accès** , sous **Autoriser les communications avec des utilisateurs fédérés** , activez ou désactivez la case à cocher **Activer la découverte du domaine partenaire** pour activer ou désactiver la découverte automatique des domaines partenaires.

6.  Cliquez sur **Valider** .

Pour activer les utilisateurs fédérés pour collaborer avec des utilisateurs de votre déploiement Lync Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) dans la documentation du déploiement ou la documentation des opérations. Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, reportez-vous à [Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) et à [Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) dans la documentation des opérations.

## Activation et désactivation de la découverte des partenaires de fédération à l’aide des applets de commande Windows PowerShell

Il est possible de gérer la découverte des partenaires de fédération à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).).

## Activer la découverte des partenaires de fédération

  - Pour activer la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à True ($True). Notez que vous devez activer le routage DNS SRV afin de changer la valeur de cette propriété.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## Désactiver la découverte des partenaires de fédération

  - Pour désactiver la découverte des partenaires de fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** à False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

