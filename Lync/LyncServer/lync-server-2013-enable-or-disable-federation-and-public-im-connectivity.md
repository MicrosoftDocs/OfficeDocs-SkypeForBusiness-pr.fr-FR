---
title: "Lync Server 2013 : Acti. ou désact. de la fédération et de la connectivité PIC"
TOCTitle: 'Activation ou désactivation de la fédération et de la connectivité PIC '
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182549(v=OCS.15)
ms:contentKeyID: 49298039
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-06-24_

La fédération doit être prise en charge pour permettre aux utilisateurs possédant un compte auprès d’un client approuvé ou d’une organisation partenaire, y compris les domaines partenaires et les utilisateurs de fournisseurs de services de messagerie instantanée publics que vous prenez en charge, de collaborer avec des utilisateurs de votre entreprise. La fédération est également nécessaire pour utiliser un fournisseur de service Exchange hébergé afin de procurer une messagerie vocale aux utilisateurs Voix Entreprise dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tel que Microsoft Exchange Online. Lorsque vous établissez une relation de confiance avec ce type de domaine externe, vous pouvez autoriser les utilisateurs de ces domaines à accéder à votre déploiement et à participer aux communications Lync Server. Cette relation de confiance est appelée « fédération » ; elle n’est pas liée à une relation de confiance Active Directory et n’en dépend pas non plus.

Pour prendre en charge l’accès des utilisateurs de domaines fédérés, vous devez activer la fédération. Si vous activez la fédération pour votre entreprise, vous devez également préciser si vous voulez implémenter les options suivantes :

  - **Activer la découverte du domaine partenaire**    Si vous activez cette option, Lync Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines non répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant des partenaires fédérés découverts et en limitant ou en bloquant ce trafic en fonction des niveaux de confiance, du volume de trafic et des paramètres de l’administrateur. Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés. Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré. Pour plus d’informations sur le contrôle de l’accès par les domaines fédérés, reportez-vous à [Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage**     Une notification d’exclusion est envoyée aux partenaires fédérés pour les informer que l’archivage est mis en œuvre dans votre déploiement. Si vous prenez en charge l’archivage des communications externes avec des domaines de partenaires fédérés, vous devez activer la notification d’exclusion relative à l’archivage afin de prévenir les partenaires que leurs messages sont archivés.

Si plus tard, vous souhaitez empêcher temporairement ou définitivement des utilisateurs d’accéder aux domaines fédérés, vous pouvez désactiver la fédération pour votre entreprise. Suivez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés dans votre entreprise, en spécifiant notamment les options de fédération que vous souhaitez prendre en charge.

> [!NOTE]  
> L’activation de la fédération pour votre organisation signifie uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés. Les utilisateurs des domaines fédérés ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de l’accès des utilisateurs fédérés. Les utilisateurs de fournisseurs de services de messagerie instantanée publics ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de la connectivité PIC. Lync Server ne peut pas utiliser de service Exchange hébergé pour fournir des services de répondeur automatique, Outlook Voice Access (y compris la messagerie vocale) ou des services de standard automatique aux utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tant que vous n’avez pas configuré de stratégie de messagerie vocale hébergée qui procure des informations de routage. Pour plus d’informations sur la configuration des stratégies de communication avec des utilisateurs de domaines fédérés dans d’autres organisations, reportez-vous à <a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</a> dans la documentation des opérations. Qui plus est, si vous souhaitez prendre en charge les communications avec des utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies à cet effet et configurer la prise en charge des différents fournisseurs de services de votre choix. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013</a> dans la documentation des opérations. Pour plus d’informations sur la création d’une stratégie de messagerie vocale hébergée, reportez-vous à <a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestion des stratégies de messagerie vocale hébergée dans Lync Server 2013</a> dans la documentation de déploiement.

## Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre entreprise

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes** , puis sur **Configuration du serveur Edge d’accès** .

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global** , sur **Modifier** , puis sur **Afficher les détails** .

5.  Dans **Modifier la configuration du serveur Edge d’accès** , effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour votre entreprise, activez la case à cocher **Autoriser les communications avec des utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour votre entreprise, désactivez la case à cocher **Autoriser les communications avec des utilisateurs fédérés** .

6.  Si vous avez activé la case à cocher **Autoriser les communications avec des utilisateurs fédérés** , procédez comme suit :
    
    1.  Pour prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **Activer la découverte du domaine partenaire** .
    
    2.  Si votre entreprise prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage** .

7.  Cliquez sur **Valider** .

Pour activer les utilisateurs fédérés pour collaborer avec des utilisateurs de votre déploiement Lync Server 2013, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) dans la documentation du déploiement ou la documentation des opérations. Pour contrôler l’accès pour des domaines fédérés spécifiques, reportez-vous à [Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation du déploiement ou la documentation des opérations.

## Activation ou désactivation de la fédération et de la connectivité PIC à l’aide des applets de commande Windows PowerShell

La fédération et la connectivité PIC peuvent également être gérées via Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer la fédération et la connectivité PIC

  - Pour activer la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## Pour désactiver la fédération et la connectivité PIC

  - Pour désactiver la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

