---
title: Réactivation du serveur après la fermeture des ports par l’Assistant Configuration de la sécurité dans les services Internet (IIS)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Réactivation du serveur après la fermeture des ports par l’Assistant Configuration de la sécurité dans les services Internet (IIS)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Certains rôles Lync Server 2013 exécutent des services Web sur Internet Information Services (IIS) 4443. L’exécution de l’Assistant Déploiement de Lync Server, Bootstrapper. exe, ou à l’aide de l’applet de action **Enable-CsComputer** crée une exception dans le pare-feu et ouvre le port. Si vous exécutez ensuite l’Assistant Configuration de la sécurité Windows Server 2008 R2 (ou d’autres scripts de renforcement), le port 4443 sera bloqué et les clients externes ne seront pas en mesure de contacter les services Web. Pour rouvrir le port, vous pouvez modifier directement l’exception de pare-feu ou réactiver le serveur.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Pour réactiver le serveur à l’aide de l’Assistant Déploiement

1.  Dans la page Assistant Déploiement de Lync Server, cliquez sur **exécuter** à côté de l' **étape 2: configurer ou supprimer les composants Lync Server**.

2.  Sur la page **Configuration des composants du serveur Lync** , cliquez sur **suivant**.

3.  Dans la page **exécution des commandes** , lorsque l’état de la tâche est affiché comme terminé, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]
    > Vous pouvez également utiliser Bootstrapper. exe ou <STRONG>Enable-CsComputer</STRONG> pour réactiver le serveur.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

