---
title: 'Lync Server 2013 : octroi d’autorisations d’unité d’organisation'
description: 'Lync Server 2013 : octroi d’autorisations d’unité d’organisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554510"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Octroi d’autorisations d’unité d’organisation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-05-14_

Vous pouvez utiliser l’applet de commande **Grant-CsOuPermission** pour accorder des autorisations à des objets dans des unités d’organisation (UO) spécifiées afin que les membres des groupes universels RTC créés par la préparation de la forêt puissent y accéder sans être membres du groupe administrateurs du domaine. Les autorisations ajoutées à l’unité d’organisation spécifiée sont les mêmes que celles que l’applet de commande **Enable-CsAdDomain** ajoute aux conteneurs ordinateurs et utilisateurs lors de la préparation du domaine.

Utilisez l’applet de commande **test-CsOuPermission** pour vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsOuPermission** .

Vous pouvez utiliser l’applet de commande **Revoke-CsOuPermission** pour supprimer les autorisations que vous avez accordées à l’aide de la cmdlet **Grant-CsOuPermission** .

<div>

## <a name="to-grant-ou-permissions"></a>Pour accorder des autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations d’unité d’organisation. Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Pour vérifier les autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’unité d’organisation que vous avez accordées à l’aide de la cmdlet **Grant-CsOuPermission** . Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Pour révoquer les autorisations d’unité d’organisation

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’unité d’organisation qui ont été accordées par la cmdlet **Grant-CsOuPermission** . Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

</div>

<span> </span>

</div>

</div>

</div>

