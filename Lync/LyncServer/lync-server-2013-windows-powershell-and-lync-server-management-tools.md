---
title: 'Lync Server 2013 : Outils de gestion de Windows PowerShell et Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Outils de gestion de Windows PowerShell et Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-07-20_

Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell. Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet. Les outils Lync Server 2013 implémentés à l’aide de Windows PowerShell incluent les éléments suivants:

  - **Générateur de topologie**. Le générateur de topologie vous permet de créer, d’ajuster et de publier votre topologie planifiée et de valider votre topologie avant de commencer les installations serveur. Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur conformément aux instructions de la topologie. After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.

  - **Lync Server Management Shell**. Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de votre déploiement.

  - **Panneau de configuration de Lync Server**. Vous pouvez utiliser l’interface utilisateur du panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes dans votre déploiement.

Ces outils utilisent des cmdlets Windows PowerShell pour la gestion de votre déploiement, y compris des applets de applet 550 spécifiques au produit. Les applets de vérification intégrés à Lync Server 2013 servent essentiellement à gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basée sur un rôle (RBAC) pour déléguer le contrôle d’administration de Lync Server 2013. Pour plus d’informations sur les applets de connexion Lync Server, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript). Les fonctionnalités de sécurité de Windows PowerShell sont conçues pour créer un environnement dans lequel les utilisateurs ne peuvent pas facilement exécuter de scripts ou sans le savoir. Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées. Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité. Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts. Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience. Pour plus d’informations, consultez sécurité du script [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Windows PowerShell à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

