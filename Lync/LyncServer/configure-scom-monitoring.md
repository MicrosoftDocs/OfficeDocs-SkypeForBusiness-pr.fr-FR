---
title: Configuration de la surveillance SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Configuration de la surveillance SCOM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Après avoir effectué la migration vers Microsoft Lync Server 2013, vous devez effectuer quelques tâches pour configurer Lync Server 2013 de manière à ce qu’il fonctionne avec System Center Operations Manager.

  - Appliquez les mises à jour de Lync Server 2010 à un serveur choisi pour gérer la logique de détection centrale.

  - Mettez à jour la clé de Registre du serveur candidat de détection centrale.

  - Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud de découverte centrale candidat.

Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.

**Appliquez les mises à jour de Lync Server 2010 à un serveur choisi pour gérer la logique de détection centrale.**

1.  Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale.

2.  Appliquez les mises à jour de Lync Server 2010 à ce serveur. Voir la rubrique [appliquer les mises à jour de Lync Server 2010](apply-lync-server-2010-updates.md).

**Mettez à jour la clé de Registre du serveur candidat de détection centrale.**

1.  Sur le serveur choisi pour gérer la logique de découverte centrale, ouvrez une fenêtre de commande Windows PowerShell.

2.  Sur la ligne de commande, tapez ce qui suit :
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > À chaque modification du Registre, une erreur liée à l’échec de la commande risque de se produire si la clé de Registre existe déjà. Dans ce cas, vous pouvez ignorer cette erreur sans risque.

    
    </div>

**Configurez votre serveur de gestion principal de System Center Operations Manager pour remplacer le nœud du service Observateur de découverte centrale candidat.**

1.  Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.

2.  Cliquez sur **Modifier l’étendue...**.

3.  Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.

4.  Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente.

Enfin, pour finaliser vos modifications, redémarrez le service de contrôle d’intégrité sur le serveur d’administration racine System Center Operations Manager.

</div>

<span> </span>

</div>

</div>

</div>

