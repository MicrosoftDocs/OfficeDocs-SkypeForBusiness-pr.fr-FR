---
title: 'Lync Server 2013 : outils de gestion Windows PowerShell et Lync Server'
description: 'Lync Server 2013 : outils de gestion Windows PowerShell et Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546040"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Outils de gestion Windows PowerShell et Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-20_

Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell comprend un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Les outils Lync Server 2013 qui sont implémentés à l’aide de Windows PowerShell sont les suivants :

  - **Générateur de topologies**. Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée, et de valider votre topologie avant de commencer les installations de serveurs. Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur comme indiqué dans la topologie. Après l’installation, les informations de configuration sont répliquées automatiquement sur tous les serveurs. Les composants ne peuvent être ajoutés à votre déploiement qu’à l’aide du générateur de topologie.

  - **Lync Server Management Shell**. Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de la ligne de commande de votre déploiement.

  - **Panneau de configuration Lync Server**. Vous pouvez utiliser l’interface utilisateur du panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes de votre déploiement.

Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, y compris presque 550 applets de commande spécifiques au produit. Les cmdlets de sécurité incluses dans Lync Server 2013 sont principalement utilisées pour gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs. Une large gamme d’applets de commande sont disponibles pour gérer l’authentification, dont certaines pour l’authentification de certificats et de codes confidentiels (PIN). De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès Role-Based (RBAC) pour déléguer le contrôle administratif de Lync Server 2013. Pour plus d’informations sur les applets de commande Lync Server, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains des problèmes de sécurité liés aux scripts de technologies plus anciennes, notamment Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité Windows PowerShell visent à créer un environnement dans lequel les utilisateurs ne peuvent pas exécuter facilement ou sans le savoir des scripts. Par défaut, les fonctionnalités de sécurité Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités afin de répondre à vos besoins de script et à divers objectifs en matière de sécurité. Cela ne signifie pas que le shell empêche les utilisateurs d’exécuter des scripts. Au lieu de cela, l’environnement de commande Exchange Management Shell complique, par défaut, les utilisateurs qui exécutent des scripts sans les utiliser. Pour plus d’informations, consultez la page relative à la sécurité des scripts Windows PowerShell à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .

</div>

<span> </span>

</div>

</div>

</div>

