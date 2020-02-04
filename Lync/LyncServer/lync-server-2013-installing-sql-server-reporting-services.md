---
title: 'Lync Server 2013 : installation de SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Installation de SQL Server Reporting Services dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-20_

Si vous envisagez d’utiliser les rapports d’analyse de Microsoft Lync Server 2013 (voir la section suivante de cette documentation pour plus d’informations), vous devez d’abord installer SQL Server Reporting Services. Reporting Services peut être installé en même temps que Microsoft SQL Server ou à tout moment après l’installation de SQL Server. Vous pouvez le faire lors de l’installation de Microsoft SQL Server ou à tout moment après l’installation de SQL Server. Si vous n’avez pas installé SQL Server, suivez les instructions fournies plus haut dans cette documentation. Lorsque vous installez SQL Server, dans la page Sélection des composants, veillez à sélectionner Reporting Services pour installer SQL Server Reporting Services.

Si vous avez déjà installé SQL Server, mais que vous n’avez pas installé SQL Server Reporting Services, vous pouvez ajouter cette fonctionnalité en suivant les instructions appropriées pour SQL Server 2008 R2 ou SQL Server 2012, selon le cas.

Pour vérifier que Reporting Services a été installé correctement, procédez comme suit :

1.  Si vous exécutez Microsoft SQL Server 2008 R2, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur **Gestionnaire de configuration de Reporting Services**.
    
    Si vous exécutez Microsoft SQL Server 2012, cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2012**, sur **outils de configuration**, puis sur **Gestionnaire de configuration Reporting Services**.

2.  Dans la boîte de dialogue **connexion de configuration de Reporting Services** , assurez-vous que le nom de votre serveur apparaît dans la zone **nom du serveur** et que le nom de l’instance SQL Server qui stocke vos données de surveillance s’affiche dans la zone instance du **serveur de rapports** . Cliquez sur **connexion**.

Dans le gestionnaire de configuration de service de création de rapports, le volet État du serveur de rapport doit indiquer que SQL Server Reporting Services est installé et que les services de Reporting sont en cours d’exécution : l’état du serveur de rapport doit être affiché comme **démarré** et le bouton **Démarrer** doit être grisé et indisponible. Si le service de création de rapports n’est pas en cours d’exécution, cliquez sur **Démarrer** pour démarrer le service.

Si aucune base de données n’est répertoriée en regard de l’étiquette de nom de la base de données du serveur de rapports, procédez comme suit :

1.  Dans le gestionnaire de configuration Reporting Services, cliquez sur **base de données**.

2.  Dans le volet base de données du serveur de rapport, cliquez sur **modifier la base de données**.

3.  Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet action, sélectionnez **créer une nouvelle base de données serveur de rapports** , puis cliquez sur **suivant**.

4.  Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet serveur de base de données, vérifiez que les informations répertoriées dans les zones **nom du serveur**, **type d’authentification**et **nom d’utilisateur** sont correctes. Cliquez sur **tester la connexion** pour vérifier qu’aucune connexion ne peut être établie avec le serveur de base de données, puis cliquez sur **suivant**.

5.  Dans l’Assistant Configuration de la base de données du serveur de rapports, dans le volet base de données, acceptez les valeurs par défaut pour **nom de la base de données**, **langue**et **mode serveur du rapport** , puis cliquez sur **suivant**.

6.  Dans l’Assistant Configuration de la base de données du serveur de rapports, dans le volet informations d’identification, vérifiez que les informations appropriées apparaissent dans la liste déroulante **type d’authentification** et dans les zones **nom d’utilisateur** et **mot de passe** , puis cliquez sur **suivant**.

7.  Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet Résumé, cliquez sur **suivant**.

8.  Dans l’Assistant Configuration de la base de données serveur de rapports, dans le volet progression et fin, cliquez sur **Terminer**.

Pour vérifier que les URL du service de création de rapports ont été configurées, cliquez sur **URL du service Web**. Une ou plusieurs URL sont indiquées sous les **URL du service Web de rapport**de titre Server. Cliquez sur chacune de ces URL pour vérifier que vous pouvez accéder à la page d’accueil de l’installation locale de SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

