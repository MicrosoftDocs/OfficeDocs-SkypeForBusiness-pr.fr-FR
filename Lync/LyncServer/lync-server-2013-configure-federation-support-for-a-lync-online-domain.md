---
title: 'Lync Server 2013 : configuration de la prise en charge de la Fédération pour un domaine Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d14f66c03ccc7def2773f7c5c8ae841b71d103
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

La Fédération avec un client Microsoft Lync Online 2010 nécessite d’effectuer les étapes suivantes :

  - Configurez la prise en charge du domaine du client Lync Online 2010 (par exemple, contoso.onmicrosoft.com). Comme indiqué dans la section [conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) de cette documentation, vous devriez déjà avoir activé la Fédération pour votre organisation. L’activation de la Fédération nécessite de spécifier la méthode à utiliser pour contrôler l’accès par les domaines fédérés. Si vous avez configuré votre organisation pour utiliser la découverte, l’ajout du domaine à la liste autorisée de votre organisation est facultatif. Si vous n’avez pas activé la découverte de domaine, vous devez ajouter le nom de domaine du client Lync Online à votre liste de domaines autorisés. Vous pouvez ajouter un nom de domaine à l’aide du panneau de configuration Lync Server ou en exécutant la cmdlet **New-CSAllowedDomain** . Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server, notamment sur l’activation de la découverte de domaines, voir [Manage SIP Federated Providers for Your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) dans la documentation des opérations. Pour plus d’informations sur l’utilisation de la cmdlet **New-CSAllowedDomain** pour ajouter un domaine, voir [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) dans la documentation des opérations.
    
    <div>
    

    > [!NOTE]  
    > Un client Lync Online peut avoir plusieurs domaines. Si vous souhaitez fédérer avec plusieurs domaines, vous devez configurer la prise en charge pour chaque domaine individuel avec lequel vous souhaitez prendre en charge la Fédération, et l’administrateur du client Lync Online doit activer la Fédération pour chacun des domaines à fédéré.

    
    </div>

  - Configurez la prise en charge du fournisseur d’hébergement du domaine Lync Online 2010 client avec lequel vous souhaitez fédérer. Utilisez la procédure décrite dans cette section pour configurer la prise en charge du fournisseur d’hébergement.
    
    <div>
    

    > [!NOTE]  
    > Cette étape est requise uniquement pour la Fédération avec un domaine d’un client Lync Online, pas pour la Fédération avec un domaine déployé sur site sur un emplacement de partenaire fédéré.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Pour configurer la prise en charge d’un fournisseur d’hébergement

1.  À partir d’un serveur frontal, démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet **New-CsHostingProvider** pour créer et configurer le fournisseur d’hébergement. Par exemple, exécutez :
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    L’exemple qui précède définit les paramètres suivants :
    
      - **Identity** spécifie un identificateur de valeur de chaîne unique pour le fournisseur d’hébergement que vous créez. Notez que la commande échoue si un fournisseur existant a déjà été configuré avec cette identité.
    
      - **ProxyFQDN** spécifie le nom de domaine complet du serveur proxy utilisé par le fournisseur d’hébergement. Cette valeur ne peut pas être modifiée. Si le fournisseur d’hébergement modifie son serveur proxy, vous devrez supprimer, puis recréer l’entrée pour ce fournisseur.
    
      - **VerificationLevel** spécifie comment (ou si) les messages envoyés à partir d’un fournisseur d’hébergement sont vérifiés pour s’assurer qu’ils ont été envoyés à partir de ce fournisseur.
    
      - **Enabled** indique si la connexion réseau entre votre domaine et le fournisseur d’hébergement est activée. Les messages ne peuvent pas être échangés entre les deux organisations tant que cette valeur n’est pas définie sur **true**.
    
      - **EnabledSharedAddressSpace** indique si le fournisseur d’hébergement est utilisé dans un scénario d’espace d’adressage SIP partagé (domaine fractionné).
    
      - **HostsOCSUsers** indique si le fournisseur d’hébergement est utilisé pour héberger les comptes Lync Server. Si la **valeur est false**, le fournisseur héberge d’autres types de comptes, tels que les comptes Microsoft Exchange.
    
      - **IsLocal** indique si le serveur proxy utilisé par le fournisseur d’hébergement est contenu dans votre topologie Lync Server.
    
    Pour plus d’informations sur l’utilisation de cette cmdlet, voir [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) dans la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

