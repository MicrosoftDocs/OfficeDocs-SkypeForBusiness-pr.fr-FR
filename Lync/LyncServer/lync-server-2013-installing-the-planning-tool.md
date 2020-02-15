---
title: 'Lync Server 2013 : installation de l’outil de planification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 792f72daac7eb1d7edb10087256bfda0912edfe9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a>Installation de l’outil de planification dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Avant de commencer à concevoir et à planifier votre infrastructure Lync Server 2013 à l’aide de l’outil de planification Microsoft Lync Server 2013, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé sur une station de travail ou un serveur qui fait partie du domaine ou de l’infrastructure dans lequel vous prévoyez d’installer Lync Server 2013. Le fichier Lisez-moi qui accompagne l’outil de planification détaille les informations importantes sur l’installation et l’utilisation de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont dupliquées ici pour plus de clarté.

<div>


> [!IMPORTANT]  
> L’outil de planification nécessite une installation par un utilisateur disposant de droits et d’autorisations d’administrateur sur l’ordinateur sur lequel l’outil doit être installé.



</div>

Les systèmes d’exploitation pris en charge pour l’installation et le fonctionnement de l’outil de planification sont les suivants :

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, édition 32 bits

  - Windows 7, 64-bit Edition à l’aide de Windows sur Win32 (WOW)

  - Windows Server 2008 R2, à l’aide de WOW

En outre, l’outil de planification nécessite Microsoft .NET Framework 4,5.

Une fois que la configuration requise pour la préinstallation est satisfaite, vous pouvez installer l’outil de planification.

<div>

## <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.

3.  Localisez le LyncPlanningTool. msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **entrée** pour exécuter le fichier.

4.  Sur la page d’accueil de l’Assistant de configuration de l' **outil de planification Microsoft Lync Server 2013**, cliquez sur **suivant**.

5.  Passez en revue le **contrat de licence utilisateur final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les conditions d’utilisation dans le contrat de licence, puis cliquez sur **suivant**.

6.  Choisissez l’emplacement d’installation des fichiers de l’outil de planification. L’emplacement par défaut est C\\: Program Files (x86\\) Microsoft Lync Server\\2013 Planning Tool. Si vous souhaitez modifier l’emplacement d’installation, cliquez sur **modifier**. Sur **modifier le dossier de destination**, parcourez ou tapez l’emplacement d’installation des fichiers, cliquez sur **OK**, puis sur **suivant**.

7.  Le programme d’installation est maintenant prêt à installer l’outil de planification. Cliquez sur **installer** pour commencer le processus d’installation.

8.  L’installation démarre et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.

9.  L’outil de planification est prêt à l’emploi.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Installation de logiciels facultatifs dans Lync Server 2013](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

