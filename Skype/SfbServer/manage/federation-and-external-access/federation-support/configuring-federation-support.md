---
title: Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online
ms.reviewer: null
'ms:assetid': e5f7f38d-ede5-4af3-88c2-026e8a78df12
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)'
'ms:contentKeyID': 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Si vous déployez Skype Entreprise dans votre organisation, vous pouvez vous fédérer avec les domaines d’un ou plusieurs Skype Entreprise Online. '
---

# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online dans Skype Entreprise Server

Vous pouvez fournir des services de communication aux utilisateurs de votre organisation de l’une des façons suivantes :

- Le déploiement Skype Entreprise Server dans votre organisation (*appelés services* locaux) et la configuration de Skype Entreprise comptes d’utilisateurs dans votre organisation.
- Configuration d’un compte client Microsoft Skype Entreprise Online auprès d’un fournisseur d’hébergement et configuration de comptes d’utilisateurs avec le fournisseur d’hébergement (*appelés services en ligne*).

Si vous déployez Skype Entreprise dans votre organisation, vous pouvez vous fédérer avec les domaines d’un ou plusieurs Skype Entreprise Online. Pour activer la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’un client Skype Entreprise Online, vous devez configurer la prise en charge du domaine et des utilisateurs du client Skype Entreprise Online.

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> Cette documentation décrit uniquement les procédures de configuration de votre organisation pour prendre en charge la fédération avec un client Skype Entreprise Online. Cette documentation ne décrit pas les procédures de configuration du client Skype Entreprise Online pour prendre en charge la fédération.

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Conditions préalables à la fédération avec un client Skype Entreprise Online

Pour vous fédérer avec un Skype Entreprise Online, vous devez avoir déjà effectué le déploiement initial et la configuration des Skype Entreprise Server dans votre organisation. Les voici :

- Déploiement d’au moins Édition Standard serveur ou d’Êdition Entreprise pool frontal dans votre organisation.
- Activation des comptes d’utilisateurs internes pour Skype Entreprise Server.
- Déploiement d’au moins un serveur Edge et des autres composants requis pour prendre en charge l’accès des utilisateurs externes. Pour plus d’informations, voir [Managing federation and external access to Skype Entreprise Server](../managing-federation-and-external-access.md).
- Activation de la prise en charge de la fédération au sein de votre organisation et configuration de la méthode appropriée pour contrôler l’accès par domaines fédérés. Pour plus d’informations, voir Activer ou désactiver [l’accès](../access-edge/enable-or-disable-remote-user-access.md) des utilisateurs [distants et Gérer les fournisseurs fédérés SIP pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
- Activation de l’accès des utilisateurs externes pour les utilisateurs de votre organisation. Pour plus d’informations, voir [Assign an external user access policy to a Skype Entreprise enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurer la prise en charge de la fédération pour un domaine Skype Entreprise Online

La fédération avec un client Skype Entreprise Online nécessite que vous complétiez les étapes suivantes :

- Configurez la prise en charge du domaine du client Skype Entreprise Online 2010 (par exemple, contoso.onmicrosoft.com). Comme indiqué dans [les conditions préalables à la fédération avec un client Skype Entreprise Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), vous devez avoir déjà activé la fédération pour votre organisation. L’activation de la fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par les domaines fédérés. Si vous avez configuré votre organisation pour utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Skype Entreprise Online à votre liste de domaines autorisés. Vous pouvez ajouter un nom de domaine à l’Skype Entreprise Server panneau de Skype Entreprise Server ou en exécutant l’cmdlet **New-CSAllowedDomain**. Pour plus d’informations sur l’utilisation Skype Entreprise Server panneau de Skype Entreprise Server, y compris l’activation de la découverte de domaines, voir Gérer les fournisseurs [fédérés SIP pour votre organisation dans Skype Entreprise Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Pour plus d’informations sur l’utilisation de l’cmdlet **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

  > [!NOTE]  
  > Un Skype Entreprise Online peut avoir plusieurs domaines. Si vous souhaitez vous fédérer avec plusieurs domaines, vous devez configurer la prise en charge de chaque domaine avec lequel vous souhaitez prendre en charge la fédération, et l’administrateur du client Skype Entreprise Online doit activer la fédération pour chacun des domaines à fédérer.

- Configurez la prise en charge du fournisseur d’hébergement du domaine Skype Entreprise Online avec lequel vous souhaitez vous fédérer. Utilisez la procédure de cette section pour configurer la prise en charge du fournisseur d’hébergement.

  > [!NOTE]  
  > Cette étape est requise uniquement pour la fédération avec un domaine d’un client Skype Entreprise Online, et non pour la fédération avec un domaine déployé en local à l’emplacement d’un partenaire fédéré.

### <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1. À partir d’un serveur frontal, démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise Server**, puis sur Skype Entreprise Server **Management Shell**.

2. Exécutez **l’cmdlet New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    L’exemple qui précède définit les paramètres suivants :

    - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échouera si un fournisseur existant a déjà été configuré avec cette identité.

    - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.

    - **VerificationLevel spécifie** comment (ou si) les messages envoyés par un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés à partir de ce fournisseur.

    - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **True**.

    - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressace SIP partagé (domaine partagé).

    - **HostsOCSUsers indique** si le fournisseur d’hébergement est utilisé pour héberger Skype Entreprise Server comptes. Si **la false**, le fournisseur héberge d’autres types de comptes, tels que Microsoft Exchange comptes.

    - **IsLocal indique** si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans Skype Entreprise Server topologie.

    Pour plus d’informations sur l’utilisation de cette cmdlet, voir [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurer l’accès des utilisateurs pour la fédération avec Skype Entreprise Online

Vous devez configurer les comptes de tous les utilisateurs de votre organisation pour qu’ils puissent communiquer avec des partenaires fédérés. Cette configuration est appliquée à tous les partenaires fédérés, y compris les domaines clients Microsoft Skype Entreprise Online avec lesquels vous supportez la fédération. Pour plus d’informations sur la configuration de la prise en charge de la fédération pour les comptes d’utilisateurs, voir [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) and [Assign an external user access policy to a Skype Entreprise enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Vérifier les communications avec un client Skype Entreprise Online dans Skype Entreprise Server

Pour permettre Skype Entreprise utilisateurs de votre organisation de communiquer avec les utilisateurs d’un client Skype Entreprise Online, vous devez avoir effectué les étapes suivantes :

- Toutes les conditions préalables sont remplies. Cela inclut le déploiement de vos serveurs internes et edge, l’activation de la prise en charge de la fédération pour votre organisation et la configuration des comptes d’utilisateurs. Pour plus d’informations, voir [Prerequisites for federating with a Skype Entreprise Online customer](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
- Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne. Cela inclut la création d’une entrée de fournisseur d’hôtes et la configuration de votre déploiement pour autoriser l’accès à Skype Entreprise domaine du client Skype Entreprise Online. Pour plus d’informations, voir [Configure federation support for a Skype Entreprise Online domain](#configure-federation-support-for-a-skype-for-business-online-domain).
- Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération. Pour plus d’informations, voir [Configure user access for federation with a Skype Entreprise Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Une fois que vous avez effectué toutes ces étapes et que l’administrateur du client Skype Entreprise Online a terminé la configuration de ses services en ligne pour prendre en charge la fédération avec votre organisation, vérifiez les communications en testant les communications entre un utilisateur interne de votre organisation et un utilisateur du client Skype Entreprise Online. Si la communication ne réussit pas, utilisez l’outil de journalisation de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème.
