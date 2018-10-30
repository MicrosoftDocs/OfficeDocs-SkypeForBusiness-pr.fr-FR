---
title: Configurer la prise en charge de la fédération pour un domaine Lync Online
TOCTitle: Configurer la prise en charge de la fédération pour un domaine Lync Online
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202166(v=OCS.15)
ms:contentKeyID: 49296412
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer la prise en charge de la fédération pour un domaine Lync Online

 

_**Dernière rubrique modifiée :** 2012-11-01_

La fédération avec un client Microsoft Lync Online 2010 nécessite les étapes suivantes :

  - Configuration de la prise en charge pour le domaine du client Lync Online 2010 (par exemple, contoso.onmicrosoft.com). Tel qu’il est spécifié dans la section [Conditions préalable à la fédération avec un client Lync Online](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de cette documentation, vous devez au préalable avoir activé la fédération pour votre organisation. Cette dernière requiert la définition de la méthode à utiliser pour contrôler l’accès par les domaines fédérés. Si vous avez configuré votre organisation de manière à utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte du domaine, vous devez ajouter le nom de domaine du client Lync Online à votre liste des domaines autorisés. Pour ce faire, vous pouvez soit utiliser le Panneau de configuration Lync Server, soit exécuter l’applet de commande **New-CSAllowedDomain**. Pour plus d’informations sur l’utilisation du Panneau de configuration Lync Server, y compris l’activation de la découverte de domaine, voir [Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation des opérations. Pour plus d’informations sur l’utilisation de l’applet de commande **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain) dans la documentation des opérations.
    
    > [!NOTE]  
    > Un client Lync Online peut avoir plusieurs domaines. Si vous souhaitez fédérer avec plusieurs domaines, vous devez configurer la prise en charge pour chaque domaine avec lequel vous souhaitez prendre en charge la fédération, et l’administrateur du client Lync Online doit activer la fédération pour chaque domaine à fédérer.

  - Configuration de la prise en charge pour le fournisseur d’hébergement du domaine client Lync Online 2010 avec lequel vous souhaitez fédérer. Utilisez la procédure de cette section pour configurer la prise en charge pour le fournisseur.
    
    > [!NOTE]  
    > Cette étape est requise uniquement pour la fédération avec le domaine d’un client Lync Online, et non pas avec un domaine quelconque déployé sur site dans un emplacement de partenaire fédéré.

## Configuration de la prise en charge pour le fournisseur d’hébergement

1.  À partir d’un serveur frontal, Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple précédent définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec le paramètre Identity.
    
      - **ProxyFQDN** spécifie le nom de domaine complet (FQDN) du serveur proxy utilisé par le fournisseur. Cette valeur ne peut pas être modifiée. Si le fournisseur modifie son serveur proxy, vous devrez supprimer puis recréer l’entrée de ce fournisseur.
    
      - **VerificationLevel** spécifie, le cas échéant, la manière dont les messages envoyés depuis le fournisseur sont vérifiés pour s’assurer de l’identité de l’émetteur.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations si la valeur n’est pas définie sur **True**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressage SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger des comptes Lync Server. Si la valeur est **False**, le fournisseur héberge d’autres types de comptes, tels que des comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est inclus dans votre topologie Lync Server.
    
    Pour en savoir plus sur l’utilisation de cette applet de commande, voir [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider) dans la documentation des opérations.

