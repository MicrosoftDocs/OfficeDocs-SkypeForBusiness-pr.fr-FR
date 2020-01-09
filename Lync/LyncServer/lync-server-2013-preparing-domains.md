---
title: 'Lync Server 2013 : Préparation des domaines'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Préparation des domaines pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

La préparation du domaine est l’étape finale de la préparation des services de domaine Active Directory pour Lync Server 2013. L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.

Vous pouvez exécuter une préparation de domaine sur n’importe quel ordinateur du domaine sur lequel vous déployez Lync Server. Vous devez préparer chacun des domaines qui hébergeront Lync Server ou des utilisateurs.

Si l’héritage des autorisations est désactivé ou que les autorisations des utilisateurs authentifiées sont désactivées au sein de votre organisation, vous devez effectuer des étapes supplémentaires lors de la préparation du domaine. Pour plus d’informations, reportez-vous à [la rubrique préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Si votre organisation utilise des unités d’organisation au lieu des trois conteneurs intégrés (c’est-à-dire, utilisateurs, ordinateurs et contrôleurs de domaine), vous devez accorder l’accès en lecture aux UO pour le groupe utilisateurs authentifiés. L’accès en lecture aux conteneurs est requis pour la préparation du domaine. Si le groupe utilisateurs authentifiés ne dispose pas d’un accès en lecture à l’unité d’organisation, exécutez l’applet de commande **Grant-CsOuPermission** comme illustré dans les exemples de code suivants pour accorder des autorisations de lecture pour chaque unité d’organisation.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Pour plus d’informations sur l’applet **de connexion Grant-CsOuPermission** , voir la documentation Lync Server Management Shell.

<div class="">


> [!TIP]  
> Pour plus d’informations sur les entrées ACE créées sur la racine du domaine et dans les conteneurs utilisateurs, ordinateurs et contrôleurs de domaine, voir <A href="lync-server-2013-changes-made-by-domain-preparation.md">modifications apportées par la préparation du domaine dans Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

