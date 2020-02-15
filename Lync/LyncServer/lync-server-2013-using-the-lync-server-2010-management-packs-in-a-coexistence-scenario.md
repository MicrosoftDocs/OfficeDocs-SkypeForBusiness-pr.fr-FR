---
title: Utilisation des packs d’administration Lync Server 2010 dans un scénario de coexistence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8014f947a669b7b636061f17e40dee0fef287345
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Utilisation des packs d’administration Lync Server 2010 dans un scénario de coexistence

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

De nombreux clients adoptent un programme de déploiement au sein de leur entreprise, dans lequel les utilisateurs sont progressivement migrés de Microsoft Lync Server 2010 vers Lync Server 2013. Les administrateurs de ces sociétés se soucient de surveiller les deux versions de Lync Server afin de s’assurer que tous les utilisateurs finaux bénéficient de la meilleure expérience de communication possible. Dans ce scénario, le pack d’administration Lync Server 2013 prend en charge un chemin de migration côte à côte avec le pack d’administration Lync Server 2010.

Dans Lync Server 2010, les ordinateurs Lync Server ont été découverts via le document de topologie stocké avec le magasin central de gestion. Dans cette configuration, un ordinateur unique signale l’existence de tous les autres ordinateurs Lync Server.

Les packs d’administration de Lync Server 2013 utilisent désormais la découverte au niveau de l’ordinateur au lieu du mécanisme de découverte central utilisé dans Lync Server 2010. Cela signifie que chaque agent System Center se découvre lui-même et signale son existence à System Center Operations Manager. L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure System Center et permet également différentes versions des packs d’administration Lync Server (par exemple, les packs d’administration pour Lync Server 2010 et les packs d’administration pour Lync Server 2013) coexister plus facilement.

Pour prendre en charge cette migration, vous devez d’abord mettre à niveau votre surveillance Lync Server 2010 existante afin d’éviter les lacunes dans la couverture. Pour ce faire, électionnez un ordinateur Lync Server 2010 existant afin de traiter le script de découverte centrale pour Lync Server 2010 avant de mettre à niveau votre magasin central de gestion vers Lync Server 2013. Il s’agit d’un processus en quatre étapes :

1.  Mettez à niveau les packs d’administration Lync Server 2010 vers la mise à jour cumulative 7.

2.  Demandez à un ordinateur Lync Server 2010 d’exécuter le script de découverte centrale.

3.  Remplacez le candidat de détection centrale dans le pack d’administration Microsoft Lync Server 2010.

4.  Vérifier que le nouveau candidat de détection centrale a été détecté.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Indiquer à un ordinateur Lync Server 2010 d’exécuter le script de détection centrale

Pour désigner un ordinateur de magasin de gestion non central (par exemple, un serveur frontal Lync Server) pour gérer la découverte centrale, vous devrez créer la clé de Registre suivante sur le serveur de magasin de gestion non central :

HKLM\\Software\\Microsoft\\Real-Time communications\\Health\\CentralDiscoveryCandidate

Vous pouvez créer cette clé de registre en procédant ainsi :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_\_local machine**, **Software**, **Microsoft**, puis **Real-Time communications**.

4.  Cliquez avec le bouton droit sur **Health**, cliquez sur **Nouveau**, sur **Clé**. Si la clé **Health** n’existe pas, cliquez avec le bouton droit sur **Real-Time Communications**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé créée, tapez Health, et appuyez sur Entrée.
    
    Une fois la nouvelle clé créée, tapez **CentralDiscoveryCandidate** et appuyez sur Entrée pour renommer la clé.

L’application de cette modification peut prendre plusieurs heures. Pour que cette modification soit appliquée immédiatement, arrêtez et redémarrez le service de l’agent d’intégrité. Pour redémarrer le service d’agent d’intégrité, effectuez la procédure suivante sur l’ordinateur Lync Server 2010 :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        Net stop HealthService

3.  Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Remplacement du candidat de détection centrale dans le pack d’administration Lync Server 2010

Après avoir demandé à un ordinateur Lync Server 2010 de générer des rapports sur les ordinateurs Lync Server 2010, vous devrez également informer le pack d’administration Lync Server 2010 de cette modification. Pour ce faire, vous devez créer un remplacement dans le pack d’administration. Pour cela, effectuez la procédure suivante :

1.  Dans la console Operations Manager, cliquez sur **Création**.

2.  Sous l’onglet Création, développez **Objets du pack d’administration**, cliquez sur **Détections d’objets**, puis sur **Étendue**.

3.  Dans la boîte de dialogue **Étendre les objets du pack d’administration**, sélectionnez l’élément avec le **Candidat de détection LS** cible, puis cliquez sur **OK**. Notez que le candidat de détection LS n’apparaîtra que si vous avez installé le pack d’administration Lync Server 2010.

4.  Dans la console Operations Manager, cliquez avec le bouton droit sur **Candidat de détection LS**, pointez sur **Remplacements**, sur **Remplacer la détection d’objets**, puis cliquez sur **Pour tous les objets de la classe : candidat de détection LS**.

5.  Dans la boîte de dialogue **Propriétés du remplacement**, cochez la case **Remplacer** en regard du paramètre **Fqdn nœud observateur détection centrale**. Tapez le nom de domaine complet de l’ordinateur Lync Server 2010 dans les zones **valeur de remplacement** et **valeur effective** . Cochez la case **Appliqué**, puis cliquez sur **OK**.

Une fois le remplacement créé, vous devez redémarrer le service de contrôle d’intégrité sur le serveur d’administration racine. Pour redémarrer le service, procédez ainsi sur le serveur d’administration racine :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, puis sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        Net stop HealthService

3.  Un message s’affiche indiquant que « Le service System Center Management est en cours d’arrêt », suivi par un second message qui vous indique que le service est arrêté. Une fois le service arrêté, vous pouvez le redémarrer en tapant la commande suivante et en appuyant sur Entrée :
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Vérification que le nouveau candidat de détection centrale a été détecté

La dernière étape avant la mise à niveau du magasin central de gestion est de s’assurer que le nouveau candidat de découverte central a été découvert par le pack d’administration Lync Server 2010. Pour ce faire, ouvrez la console Operations Manager, puis cliquez sur Analyse. Sous l’onglet Analyse, développez **Intégrité Microsoft Lync Server 2010**, **Découverte de la topologie**, puis cliquez sur **Affichage des états de détection**. Vérifiez qu’une ligne de l’affichage comprend un **Chemin** qui répertorie le nom de domaine complet du candidat de détection central. Vérifiez également que l’état de l’ordinateur est **Sain**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

