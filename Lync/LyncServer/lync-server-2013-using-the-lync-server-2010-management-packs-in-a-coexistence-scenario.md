---
title: Utiliser les packs d’administration de Lync Server 2010 dans un scénario de coexistence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Utiliser les packs d’administration de Lync Server 2010 dans un scénario de coexistence

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

De nombreux clients adoptent un programme de déploiement au sein de leur entreprise, dans lequel les utilisateurs sont progressivement migrés de Microsoft Lync Server 2010 vers Lync Server 2013. Les administrateurs de ces entreprises se soucient de surveiller les deux versions de Lync Server pour s’assurer que tous leurs utilisateurs finaux bénéficient d’une meilleure utilisation de communication possible. Dans le cas présent, le pack d’administration de Lync Server 2013 prend en charge un chemin de migration côte à côte avec le pack d’administration de Lync Server 2010.

Sur Lync Server 2010, les ordinateurs Lync Server étaient détectés par le biais du document topologique stocké auprès du magasin central de gestion. Dans cette configuration, un ordinateur unique signale l’existence de tous les autres ordinateurs Lync Server.

Les packs de gestion pour Lync Server 2013 utilisent désormais une découverte au niveau de l’ordinateur au lieu du mécanisme de découverte centralisé utilisé dans Lync Server 2010. Cela signifie que chaque agent système Centre de systèmes Découvre son existence et signale son existence à System Center Operations Manager. L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure de centre système et permet d’utiliser différentes versions des packs de gestion Lync Server (par exemple, les packs d’administration de Lync Server 2010 et les packs de gestion pour Lync Server 2013) pour pouvoir cohabiter plus facilement.

Pour prendre en charge cette migration, vous devez tout d’abord mettre à niveau votre analyse Lync Server 2010 existante afin d’éviter les lacunes en couverture. Pour cela, vous devez choisir un ordinateur Lync Server 2010 existant pour gérer le script de découverte central pour Lync Server 2010 avant de mettre à niveau votre magasin de gestion centrale vers Lync Server 2013. Il s’agit d’un processus en quatre étapes:

1.  Effectuez la mise à niveau des packs d’administration de Lync Server 2010 vers la mise à jour cumulative 7.

2.  Demandez à un ordinateur 2010 Lync Server d’exécuter le script de découverte central.

3.  Remplacez le candidat de découverte central dans Microsoft Lync Server 2010 Management Pack.

4.  Vérifiez que le nouveau prototype de découverte centralisé a été découvert.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Demande à un ordinateur Lync Server 2010 d’exécuter le script de découverte central

Pour nommer un serveur du magasin de gestion non central (par exemple, un serveur frontal Lync Server) pour gérer la découverte centralisée, vous devez créer la clé de Registre suivante sur le serveur du magasin de gestion non central:

Programme\\HKLM\\logiciel\\Microsoft CentralDiscoveryCandidate de l'\\intégrité\\des communications en temps réel

Vous pouvez créer cette clé de registre en effectuant les étapes suivantes:

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l’application **HKEY\_\_local**, développez **logiciel**, développez **Microsoft**, puis développez **communications en temps réel**.

4.  Cliquez avec le bouton droit sur **État**, cliquez sur **nouveau**, puis sur **clé**. S’il n’existe pas de clé d' **intégrité** , cliquez avec le bouton droit sur **communications en temps réel**, pointez sur **nouveau**, puis cliquez sur **clé**. Lorsque la nouvelle clé est créée, tapez santé, puis appuyez sur entrée.
    
    Une fois la nouvelle clé créée, tapez **CentralDiscoveryCandidate** , puis appuyez sur entrée pour renommer la clé.

Le choix de l’ordinateur est susceptible de durer quelques heures. Pour que la modification prenne effet immédiatement, arrêtez, puis redémarrez le service agent d’intégrité. Pour redémarrer le service agent d’intégrité, procédez comme suit sur l’ordinateur Lync Server 2010:

1.  Cliquez sur **Démarrer**, **sur tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée:
    
        Net stop HealthService

3.  Un message s’affiche, indiquant que le service de gestion de centre de systèmes s’arrête, suivi d’un deuxième message vous indiquant que le service a été arrêté. Lorsque le service s’est arrêté, vous pouvez le redémarrer en entrant la commande suivante et en appuyant sur entrée:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Remplacement du candidat de découverte central dans le pack d’administration de Lync Server 2010

Après avoir demandé à un ordinateur Lync Server 2010 de signaler des ordinateurs Lync Server 2010, vous devez en informer le pack d’administration de Lync Server 2010 à propos de cette modification. Pour cela, vous devez créer un remplacement dans le pack d’administration. Pour cela, procédez comme suit:

1.  Dans la console Operations Manager, cliquez sur **création**.

2.  Dans l’onglet création, développez **objets du pack d’administration**, cliquez sur **découvertes d’objets**, puis cliquez sur **étendue**.

3.  Dans la boîte de dialogue **objets du pack d’administration** d’étendues, sélectionnez l’élément avec le **candidat de découverte Target LS** , puis cliquez sur **OK**. Notez que le prototype de découverte ne s’affichera que si vous avez installé le pack d’administration 2010 de Lync Server.

4.  Dans la console Operations Manager, cliquez avec le bouton droit sur **candidat de découverte de LS**, pointez sur **remplacements**, pointez sur **remplacer la découverte d’objets**, puis cliquez sur **tous les objets de classe: ls découverte candidat**.

5.  Dans la boîte de dialogue **Propriétés de remplacement** , activez la case à cocher **remplacer** en regard du **nom de domaine complet de découverte WatcherNode**. Tapez le nom de domaine complet de l’ordinateur Lync Server 2010 dans les zones **valeur de remplacement** et **valeur effective** . Cochez la case **appliqué** , puis cliquez sur **OK**.

Une fois que vous avez créé la substitution, vous devez redémarrer le service d’intégrité sur le serveur de gestion racine. Pour redémarrer le service d’intégrité, procédez comme suit sur le serveur de gestion racine:

1.  Cliquez sur **Démarrer**, **sur tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée:
    
        Net stop HealthService

3.  Un message s’affiche, indiquant que le service de gestion de centre de systèmes s’arrête, suivi d’un second message indiquant que le service a été arrêté. Lorsque le service s’est arrêté, vous pouvez le redémarrer en entrant la commande suivante et en appuyant sur entrée:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Vérifier que le nouveau candidat de découverte centralisé a été découvert

Avant de procéder à la mise à niveau du magasin centralisé de gestion, vous devez vous assurer que le nouveau prototype de découverte central a été détecté par le pack d’administration 2010 de Lync Server. Pour cela, ouvrez la console Operations Manager, puis cliquez sur surveillance. Dans l’onglet analyse, développez **État de Microsoft Lync Server 2010**, développez découverte de la **topologie**, puis cliquez sur **affichage État de découverte**. Vérifiez qu’une ligne dans l’affichage comporte un **chemin d’accès** qui recense le nom de domaine complet de la fonction de découverte centrale. Vous devez également vérifier que l’état de l’ordinateur est **correctement**signalé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

