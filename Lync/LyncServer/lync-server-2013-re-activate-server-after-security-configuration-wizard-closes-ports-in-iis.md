---
title: Réactiver le serveur après la fermeture des ports par l’Assistant Configuration de sécurité dans les services Internet (IIS)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512041"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Réactiver le serveur après la fermeture des ports par l’Assistant Configuration de sécurité dans les services Internet (IIS)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Certains rôles Lync Server 2013 exécutent des services Web sur le port 4443 des services Internet (IIS). L’exécution de l’Assistant Déploiement de Lync Server, Bootstrapper.exe ou l’utilisation de l’applet de commande **Enable-CsComputer** crée une exception dans le pare-feu et ouvre le port. Si vous exécutez ensuite l’Assistant Configuration de la sécurité Windows Server 2008 R2 (ou d’autres scripts de renforcement de la protection), le port 4443 sera bloqué et les clients externes ne pourront pas contacter les services Web. Pour rouvrir le port, vous pouvez modifier directement l’exception de pare-feu ou réactiver le serveur.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Pour réactiver le serveur à l’aide de l’Assistant Déploiement

1.  Sur la page Assistant Déploiement Lync Server, cliquez sur **exécuter** à côté de **étape 2 : installer ou supprimer des composants Lync Server**.

2.  Sur la page **Installer les composants Lync Server**, cliquez sur **Suivant**.

3.  Sur la page **Exécution de commandes**, lorsque l’état indique que la tâche est terminée, cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]
    > Vous pouvez également utiliser bootstrapper.exe ou <STRONG>Enable-CsComputer</STRONG> pour réactiver le serveur.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

