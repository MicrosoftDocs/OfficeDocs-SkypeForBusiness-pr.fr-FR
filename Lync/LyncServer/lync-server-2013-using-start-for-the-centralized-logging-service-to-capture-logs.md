---
title: Utiliser le service de connexion centralisé pour capturer les journaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Utiliser démarrer pour le service de journalisation centralisé pour capturer les journaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Pour capturer les journaux de suivi à l’aide du service de journalisation centralisé, vous devez exécuter une commande pour commencer à vous connecter sur un ou plusieurs ordinateurs et pools. Vous émettez également des paramètres qui définissent les ordinateurs ou les pools, scénarios d’exécution (par exemple, AlwaysOn, autre scénario prédéfinie ou scénario que vous avez créé), les composants serveur Lync (par exemple, S4, SipStack) à tracer.

Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat. Dans le service de journalisation centralisé, un scénario est le concept d’activation de la journalisation en fonction d’une collection de composants serveur, de niveaux de connexion et d’indicateurs, qui est beaucoup plus efficace et utile que de définir ces éléments pour chaque serveur. Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.

Le scénario par défaut s’appelle **AlwaysOn**. Comme son nom l’indique, AlwaysOn a pour objectif d’exécuter le scénario de manière constante. Le scénario AlwaysOn collecte des informations (notez que le niveau de journalisation des messages Info comprend, en plus des messages Info, les messages Error, Fatal et Warning) concernant bon nombre des composants serveur les plus courants. AlwaysOn collecte des informations avant, pendant et après la survenue d’un problème, comportement totalement différent des précédents outils de journalisation, tels que OCSLogger. Auparavant, vous exécutiez OCSLogger une fois le problème survenu, ce qui compliquait davantage la résolution des erreurs, car les données dont vous disposiez étaient réactives, et non pas proactives. Si AlwaysOn ne contient pas les informations que vous cherchez pour identifier le composant qui pose problème et d’indiquer la procédure corrective appropriée (ce qui est peu probable, étant donné l’ampleur et la profondeur des fournisseurs dans AlwaysOn), il indiquera un niveau raisonnable d’informations permettant de déterminer les autres opérations requises, par exemple créer un scénario, collecter d’autres informations, lancer une recherche différente afin de collecter des informations plus détaillées, etc.

Le service de journalisation centralisé fournit deux moyens d’émettre des commandes. Plusieurs rubriques ont été focalisées dans le cadre de l’utilisation de Windows PowerShell par le biais de Lync Server Management Shell. La possibilité d’utiliser un certain nombre de configurations et de commandes complexes favorise l’utilisation de Windows PowerShell pour le service de journalisation centralisée. Étant donné que Windows PowerShell via Lync Server Management Shell est presque omniprésent pour toutes les fonctions de Lync Server, seules les commandes Windows PowerShell sont abordées.

<div>


> [!NOTE]
> Si vous décidez d’utiliser le jeu de commandes limité disponible à partir de la ligne de commande, vous pouvez obtenir de l’aide <CODE>ClsController.exe</CODE>sur CLSController. exe en le tapant. Par défaut, <STRONG>ClsController. exe</STRONG> est installé dans le répertoire C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Pour exécuter démarrer-CsClsLogging avec Windows PowerShell en utilisant les commandes de base

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Démarrez un scénario de journalisation avec le service de journalisation centralisée en entrant la commande suivante:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Pour lancer le scénario **AlwaysOn**, par exemple, tapez :
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Le scénario AlwaysOn n’a pas de durée par défaut. Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande <STRONG>Stop-CsClsLogging</STRONG>. Pour plus d’informations, voir <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Pour tous les autres scénarios, la durée par défaut est de 4 heures.

    
    </div>

3.  Appuyez sur Entrée pour exécuter la commande.
    
    <div>
    

    > [!NOTE]
    > L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peuvent prendre quelques instants (de 30 à 60 secondes).

    
    </div>
    
    ![Exécution de Start-CsClsLogging.] (images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Exécution de Start-CsClsLogging.")

4.  Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging** associée au nom du scénario supplémentaire à exécuter (par exemple, le scénario **Authentification**) :
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment. Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux. Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario. Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools. Pour plus d’informations sur la gestion des scénarios en cours d’exécution, voir <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation de l’application arrêt pour le service de journalisation centralisée dans Lync Server 2013</A> et <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">arrêt-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser –Duration pour définir la durée d’exécution d’un scénario. Vous pouvez également définir –Computers, une liste de noms complets d’ordinateurs séparés par une virgule ou –Pools, une liste de noms complets de pools séparés par une virgule sur lesquels vous souhaitez exécuter la journalisation.
    
    Vous démarrez une session de journalisation pour le scénario *UserReplicator* sur le pool «pool01.contoso.net». Vous pouvez également définir la durée de la session de journalisation à 8 heures. Pour cela, tapez :
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :
    
    ![Exécution de Start-CsClsLogging.] (images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Exécution de Start-CsClsLogging.")
    
    Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Présentation du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

