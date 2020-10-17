---
title: 'Lync Server 2013 : problèmes liés au test de topologie'
description: 'Lync Server 2013 : problèmes liés au test de la topologie.'
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
ms.openlocfilehash: 2a0f24942844bcf371eff94ee04c8faafcf513d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554440"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problèmes avec le test de topologie dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

À l’instar de la cmdlet **test-CsTopology** , Best Practices Analyzer vous offre un moyen de vérifier que Lync Server 2013 fonctionne correctement à un niveau global. Par défaut, Best Practice Analyzer, comme l’applet de commande, vérifie l’ensemble de votre infrastructure Lync Server 2013, en vérifiant que les services requis sont en cours d’exécution et que les droits et autorisations d’utilisateur appropriés ont été définis pour ces services et pour les groupes de sécurité universels créés lors de l’installation de Lync Server 2013.

En plus de vérifier la validité de Lync Server dans son ensemble, **test-CsTopology** vérifie également la validité d’un service spécifique. Pour plus d’informations sur l’utilisation de l’applet de commande pour tester des services spécifiques, voir [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) dans la documentation de Lync Server Management Shell. Utilisez les informations suivantes pour vous aider à résoudre les problèmes liés à votre topologie.

<div>


> [!NOTE]  
> Selon la configuration de vos serveurs Edge et des paramètres de réseau de périmètre associés, notamment les paramètres de pare-feu et les autorisations, il se peut que l’outil Best Practices Analyzer ne puisse pas accéder à vos serveurs Edge et en faire l’analyse. Si vous incluez des serveurs Edge dans votre analyse et que les rapports indiquent qu’il existe un problème d’accès aux serveurs Edge, désactivez la case à cocher <STRONG>serveurs Edge</STRONG> et exécutez à nouveau l’analyse pour empêcher que le problème n’apparaisse dans les rapports.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Résolution des problèmes liés à votre topologie

Si le test de topologie a détecté des problèmes avec votre topologie, ces problèmes sont probablement dus à des problèmes survenus lors de la publication ou de l’activation de votre topologie.

Lorsque vous modifiez votre topologie, les modifications ne prennent effet que lorsqu’elles ont été publiées et activées. Vous devez utiliser le générateur de topologie pour effectuer des modifications de topologie. Une fois que vous avez apporté des modifications, vous pouvez les publier et les activer à l’aide du générateur de topologie.

Lorsque vous publiez les modifications, les nouvelles informations (par exemple, un nouveau site ou un nouveau rôle serveur) sont écrites dans le magasin central de gestion. Toutefois, ces nouveaux objets (ou les objets récemment modifiés) ne rejoignent pas immédiatement votre topologie. Les objets rejoignent votre topologie uniquement lorsque vous activez la topologie mise à jour. Si vous sélectionnez l’option publier dans le générateur de topologie, ces deux étapes se produisent : les modifications sont publiées (c’est-à-dire qu’elles sont écrites dans le magasin central de gestion), puis la nouvelle topologie est activée.

Par défaut, les membres du groupe RTCUniversalServerAdmins sont autorisés à exécuter l’applet de commande **Publish-CsTopology** et la cmdlet **Enable-CsTopology** . Toutefois, si les autorisations de configuration n’ont pas été déléguées, vous devez être connecté en tant qu’administrateur de domaine pour exécuter **Publish-CsTopology**. Pour donner à RTCUniversalServerAdmins le droit d’utiliser réellement l’applet de commande **Publish-CsTopology** , vous devez exécuter la cmdlet **Grant-CsSetupPermission** sur chaque conteneur Active Directory qui contient des ordinateurs exécutant les services Lync Server. Pour donner à RTCUniversalServerAdmins le droit d’utiliser la cmdlet **Enable-CsTopology** , vous devez exécuter l’applet de commande **Set-CsSetupPermission** sur chaque conteneur des services de domaine Active Directory qui contient des ordinateurs exécutant les services Lync Server. Notez que cette option s’applique à l’activation et à la publication d’une topologie à l’aide du générateur de topologie. Si vous n’avez pas délégué d’autorisations à l’aide de **Set-CsSetupPermission**, seul un administrateur de domaine peut activer et publier une topologie via le générateur de topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

