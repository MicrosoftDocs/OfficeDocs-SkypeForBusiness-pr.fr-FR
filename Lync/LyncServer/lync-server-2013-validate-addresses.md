---
title: 'Lync Server 2013 : validation des adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf8ebf2dd3da00adbd4719dd749c59eeeee82b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508621"
---
# <a name="validate-addresses-in-lync-server-2013"></a>Valider des adresses dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Avant de publier la base de données des emplacements, vous devez valider les nouveaux emplacements par rapport à la base de données MSAG (Master Street Address Guide) gérée par votre fournisseur de service de jonction SIP ou E9-1-1 PSTN (Public Switched Telephone Network).

Pour plus d’informations sur les fournisseurs de services de jonction SIP E9-1-1, voir [choix d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Pour plus d’informations sur la validation des adresses, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Pour valider des adresses situées dans la base de données des emplacements

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez les applets de commande suivantes pour configurer la connexion du fournisseur de service d’urgence.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Exécutez l’applet de commande suivante pour valider les adresses de la base de données des emplacements.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.

</div>

</div>

<span> </span>

</div>

</div>

</div>

