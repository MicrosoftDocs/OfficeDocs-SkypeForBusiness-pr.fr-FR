---
title: 'Lync Server 2013 : problèmes liés au test de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problèmes liés au test topologique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

À l’instar de l’applet **de contrôle test-CsTopology** , le meilleur analyseur de pratique vous offre la possibilité de vérifier que Lync Server 2013 fonctionne correctement à un niveau global. Par défaut, l’analyseur de meilleures pratiques, à l’instar de l’applet de contrôle, vérifie l’intégralité de votre infrastructure Lync Server 2013, en vérifiant que les services requis sont en cours d’exécution et que les droits d’utilisateur et les autorisations appropriés ont été définis pour ces services et pour le universel. groupes de sécurité créés lors de l’installation de Lync Server 2013.

En plus de vérifier la validité du serveur Lync, **test-CsTopology** vérifie également la validité d’un service spécifique. Pour plus d’informations sur l’utilisation de l’applet de contrôle pour tester des services spécifiques, consultez la rubrique [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) dans la documentation Lync Server Management Shell. Utilisez les informations suivantes pour vous aider à résoudre les problèmes liés à votre topologie.

<div>


> [!NOTE]  
> En fonction de la configuration de votre serveur Edge et des paramètres de réseau de périmètre associés, y compris les paramètres de pare-feu et les autorisations, l’analyseur de meilleures pratiques peut ne pas être en mesure d’accéder aux serveurs Edge et de les analyser. Si vous incluez des serveurs de périphérie dans votre numérisation et que les rapports indiquent qu’il y a un problème pour accéder aux serveurs Edge, désactivez la case à cocher <STRONG>serveurs de périphérie</STRONG> et relancez la numérisation pour éviter que le problème ne s’affiche dans les rapports.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Résoudre les problèmes liés à votre topologie

Si le test de topologie a détecté des problèmes avec votre topologie, ces problèmes sont probablement causés par des problèmes qui se sont produits lorsque vous avez publié ou activé votre topologie.

Lorsque vous apportez des modifications à votre topologie, celles-ci ne s’appliquent que lorsque vous les avez publiées et activées. Vous devez utiliser le générateur de topologie pour apporter des changements de topologie. Après avoir apporté des modifications, vous pouvez publier et activer ces modifications à l’aide du générateur de topologie.

Lorsque vous publiez les modifications, les nouvelles informations (par exemple, un nouveau site ou un nouveau rôle serveur) sont écrites dans le magasin de gestion central. Toutefois, ces nouveaux objets (ou les modifications que vous avez apportées) ne rejoignent pas immédiatement votre topologie. Les objets rejoignent votre topologie uniquement lors de l’activation de la topologie mise à jour. Si vous sélectionnez l’option publier dans le générateur de topologie, les deux étapes suivantes se produisent : les modifications sont publiées (c’est-à-dire qu’elles sont écrites dans le magasin de gestion central), puis la nouvelle topologie est activée.

Par défaut, les membres du groupe RTCUniversalServerAdmins sont autorisés à exécuter l’applet de cmdlet **publishe-CsTopology** et l’applet de passe **Enable-CsTopology** . Toutefois, si vous n’avez pas encore délégué d’autorisations d’installation, vous devez être connecté en tant qu’administrateur de domaine pour exécuter la **fonction de publication-CsTopology**. Pour permettre à RTCUniversalServerAdmins de faire réellement appel à l’applet de contrôle **Publisher-CsTopology** , vous devez exécuter l’applet de contrôle **Grant-CsSetupPermission** dans chaque conteneur Active Directory contenant des ordinateurs exécutant des services serveur Lync. Pour permettre à RTCUniversalServerAdmins d’utiliser l’applet de contrôle **Enable-CsTopology** , vous devez exécuter l’applet **de contrôle Set-CsSetupPermission** sur chaque conteneur services de domaine Active Directory qui contient les ordinateurs exécutant Lync Server services. Notez que cela s’applique à l’activation et la publication d’une topologie à l’aide du générateur de topologie. Si vous n’avez pas d’autorisations déléguées à l’aide de **Set-CsSetupPermission**, seul un administrateur de domaine peut activer et publier une topologie via le générateur de topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

