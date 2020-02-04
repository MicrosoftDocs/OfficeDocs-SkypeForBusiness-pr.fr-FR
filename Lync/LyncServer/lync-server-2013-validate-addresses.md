---
title: 'Lync Server 2013 : valider les adresses'
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Valider des adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-17_

Avant de publier la base de données de géolocalisation, vous devez valider de nouveaux emplacements par rapport au Guide de l’adresse principale (MSAG), qui est géré par votre réseau SIP ou un réseau téléphonique commuté (RTC) E9-1-1 prestataire de services.

Pour plus d’informations sur les fournisseurs de services SIP Trunk E9-1-1, voir [choix d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Pour plus d’informations sur la validation d’adresses, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Pour valider des adresses situées dans la base de données des emplacements

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez les applets de commande ci-dessous pour configurer la connexion du fournisseur de service d’urgence.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Exécutez l’applet de commande ci-dessous pour valider les adresses de la base de données des emplacements.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.

</div>

</div>

<span> </span>

</div>

</div>

</div>

