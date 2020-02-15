---
title: 'Lync Server 2013 : installation des fichiers de l’agent Operation Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48624e3f93ebb133743680a01399444137385a0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Installation des fichiers de l’agent Operation Manager dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Pour installer les fichiers de l’agent Operations Manager sur l’ordinateur, procédez comme suit.

1.  Sur le support d’installation de System Center, double-cliquez sur **SetupOM. exe**.

2.  Dans le programme d’installation de System Center Operation Manager, cliquez sur **installer l’agent Operations Manager**.

3.  Dans l’Assistant Installation de System Center, dans la page **Bienvenue dans l’Assistant Installation de System Center Operations Manager** , cliquez sur **suivant**.

4.  Sur la page **dossier de destination** , sélectionnez le dossier dans lequel les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **suivant**.

5.  Dans la page **configuration du groupe d’administration** , sélectionnez spécifier les informations du groupe d' **administration**, puis cliquez sur **suivant**.

6.  Dans la page **configuration du groupe d’administration** , tapez le nom de votre groupe d’administration Operations Manager dans la zone Nom du groupe d' **administration** , puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, ATL-SCOM-001) dans la zone serveur d' **administration** . Si vous avez modifié le numéro de port utilisé par Operations Manager, tapez le nouveau numéro de port dans la zone port du serveur d’administration. Dans le cas contraire, laissez le port à la valeur par défaut 5723 et cliquez sur **suivant**.

7.  Sur la page **compte d’action d’agent** , sélectionnez **système local**, puis cliquez sur **suivant**.

8.  Sur la page **Microsoft Update** , sélectionnez **je ne souhaite pas utiliser Microsoft Update**, puis cliquez sur **suivant**.

9.  Sur la page **prêt pour l’installation** , cliquez sur **installer**.

10. Sur la page **fin de l’Assistant Installation de System Center Operations Manager** , cliquez sur **Terminer**.

11. Cliquez sur **Quitter**.

Si vous utilisez System Center 2007 R2, vous pouvez vérifier que l’agent a bien été créé en cliquant sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2007 R2**, puis en cliquant sur **environnement gestionnaire des opérations**. Dans l’environnement de ligne de commande Operations Manager, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :

    Get-Agent 

Une liste de tous vos agents Operations Manager apparaît à l’écran.

Si vous utilisez System Center 2012, exécutez cette commande à partir du shell du gestionnaire des opérations 2012 :

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

