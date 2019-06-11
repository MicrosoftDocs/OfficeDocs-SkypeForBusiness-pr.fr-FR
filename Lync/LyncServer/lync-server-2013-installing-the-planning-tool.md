---
title: 'Lync Server 2013 : Installation de l’outil de planification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e528062d5fd04e1a11df934cbc01b2dc8c92aa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a>Installation de l’outil de planification dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Avant de commencer à concevoir et à planifier votre infrastructure Lync Server 2013 à l’aide de l’outil de planification Microsoft Lync Server 2013, vous devez commencer par installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé vers une station de travail ou un serveur qui fait partie de l’infrastructure ou du domaine sur lequel vous envisagez d’installer Lync Server 2013. Le fichier Lisez-moi fourni avec les détails de l’outil de planification est une information importante sur son installation et son utilisation. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.

<div>


> [!IMPORTANT]  
> L’outil de planification nécessite une installation par un utilisateur disposant de droits d’administrateur et d’autorisations sur l’ordinateur sur lequel l’outil doit être installé.



</div>

Les systèmes d’exploitation pris en charge pour l’installation et l’exécution de l’outil de planification sont les suivants:

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, édition 32 bits

  - Windows 7, édition 64 bits avec WOW (Windows on Win32)

  - Windows Server 2008 R2 avec WOW

Par ailleurs, l’outil de planification nécessite Microsoft .NET Framework 4,5.

Après avoir satisfait la configuration requise, vous pouvez ensuite installer l’outil de planification.

<div>

## <a name="to-install-the-planning-tool"></a>Pour installer l’outil de planification

1.  Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2.  À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.

3.  Recherchez le fichier LyncPlanningTool. msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.

4.  Dans la page Bienvenue de l' **Assistant Installation de Microsoft Lync Server 2013,** cliquez sur **suivant**.

5.  Passez en revue le **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant**.

6.  Choisissez où vous souhaitez installer les fichiers de l’outil de planification. Par défaut, il s’agit\\de l’emplacement par défaut\\C: Program Files\\(x86) Microsoft Lync Server 2013 Planning. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier**. Dans **Modifier le dossier de destination**, accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK**, puis sur **Suivant**.

7.  Le programme d’installation est désormais prêt à installer l’outil de planification. Cliquez sur **Installer** pour commencer le processus d’installation.

8.  L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer**.

9.  L’outil de planification est prêt à l’emploi.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Installer un logiciel facultatif dans Lync Server 2013](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

