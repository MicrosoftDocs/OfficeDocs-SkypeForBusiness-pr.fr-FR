---
title: 'Lync Server 2013 : préparation des domaines'
description: 'Lync Server 2013 : préparation des domaines.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7700bbdd10a96949f892858ae03da8de60d86a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549980"
---
# <a name="preparing-domains-for-lync-server-2013"></a>Préparation des domaines pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

La préparation du domaine est la dernière étape de la préparation des services de domaine Active Directory pour Lync Server 2013. L’étape de préparation du domaine ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui accordent les autorisations d’hébergement et de gestion des utilisateurs dans le domaine. La préparation du domaine créé des entrées de contrôle d’accès sur la racine du domaine et dans trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine.

Vous pouvez exécuter la préparation de domaine sur n’importe quel ordinateur du domaine où vous déployez Lync Server. Vous devez préparer tous les domaines qui hébergeront Lync Server ou les utilisateurs.

Si l’héritage des autorisations ou les autorisations des utilisateurs authentifiés sont désactivés dans votre organisation, la procédure de préparation du domaine comporte des étapes supplémentaires. Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Si votre organisation utilise des unités d’organisation à la place des trois conteneurs intégrés (Utilisateurs, Ordinateurs et Contrôleurs de domaine), le groupe Utilisateurs authentifiés doit disposer d’un accès en lecture aux unités d’organisation. L’accès en lecture aux conteneurs est obligatoire pour la préparation du domaine. Si tel n’est pas le cas, exécutez l’applet de commande **Grant-CsOuPermission** comme illustré dans les exemples de code suivants afin d’accorder des autorisations de lecture pour chaque unité d’organisation.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Pour plus d’informations sur l’applet de commande **Grant-CsOuPermission** , voir la documentation de Lync Server Management Shell.

<div class="">


> [!TIP]  
> Pour plus d’informations sur les ACE créées sur la racine du domaine et dans les conteneurs utilisateurs, ordinateurs et contrôleurs de domaine, voir <A href="lync-server-2013-changes-made-by-domain-preparation.md">modifications apportées par le domaine en préparation dans Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Utilisation d’applets de commande pour inverser la préparation du domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

