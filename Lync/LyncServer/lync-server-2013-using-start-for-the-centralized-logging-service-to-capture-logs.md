---
title: Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b32a746f6614ea72e9f0f085a3d3731969cf5f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour capturer les journaux de suivi à l’aide du service de journalisation centralisée, vous devez émettre une commande pour commencer la journalisation sur un ou plusieurs ordinateurs et pools. Vous pouvez également émettre des paramètres qui définissent les ordinateurs ou pools, les scénarios à exécuter (par exemple, AlwaysOn, un autre scénario prédéfini ou un scénario que vous avez créé), les composants Lync Server (par exemple, S4, SipStack) à suivre.

Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat. Dans le service de journalisation centralisée, un scénario est le concept de l’ouverture de session basée sur une collection de composants serveur, de niveaux de journalisation et d’indicateurs, ce qui est bien plus efficace et utile que la définition de ces éléments sur une base par serveur. Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.

Le scénario par défaut est appelé **AlwaysOn**. Comme son nom l’indique, AlwaysOn est constamment exécuté. Le scénario AlwaysOn recueille des informations de niveau de journalisation Info (notez que le niveau de journalisation Info inclut les messages d’erreur fatale, d’erreur et d’avertissement en plus des messages Info) pour de nombreux composants serveur parmi les plus courants. AlwaysOn recueille des informations avant, pendant et après qu’un problème se produit. Ce comportement est considérablement différent du comportement type des anciens outils de journalisation tels qu’OCSLogger. Vous deviez en effet exécuter OCSLogger après qu’un problème se soit produit, ce qui rendait la résolution plus difficile, car les données dont vous disposiez étaient réactives et non proactives. Si AlwaysOn ne contient pas les informations que vous recherchez concernant le composant à l’origine du problème et vous indiquant la marche à suivre pour le résoudre (ce qui ne risque pas d’être le cas étant donnée les informations fournies par AlwaysOn), il fournit un niveau raisonnable d’informations pour déterminer les autres actions que vous devez effectuer, comme créer un nouveau scénario, recueillir d’autres informations, exécuter une autre recherche pour obtenir des détails plus précis, etc.

Le service de journalisation centralisée offre deux méthodes d’émission de commandes. Un certain nombre de sujets ont été axés sur l’utilisation de Windows PowerShell via Lync Server Management Shell. La possibilité d’utiliser un certain nombre de configurations et de commandes complexes favorise Windows PowerShell pour l’utilisation du service de journalisation centralisée. Étant donné que Windows PowerShell via Lync Server Management Shell est presque omniprésent pour toutes les fonctions dans Lync Server, seules les commandes Windows PowerShell sont abordées.

<div>


> [!NOTE]
> Si vous décidez d’utiliser le jeu de commandes limité disponible à partir de la ligne de commande, vous pouvez obtenir de l’aide <CODE>ClsController.exe</CODE>sur CLSController. exe en tapant. Par défaut, <STRONG>ClsController. exe</STRONG> est installé dans le répertoire C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes de base

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Démarrez un scénario de journalisation avec le service de journalisation centralisée en tapant ce qui suit :
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Par exemple, pour lancer le scénario **AlwaysOn**, tapez :
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Le scénario AlwaysOn n’a pas de durée par défaut. Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande <STRONG>Stop-CsClsLogging</STRONG>. Pour plus d’informations, voir <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Pour tous les autres scénarios, la durée par défaut est de 4 heures.

    
    </div>

3.  Appuyez sur Entrée pour exécuter la commande.
    
    <div>
    

    > [!NOTE]
    > L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peut prendre quelques instants (de 30 à 60 secondes).

    
    </div>
    
    ![Exécution de Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Exécution de Start-CsClsLogging.")

4.  Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging**, avec le nom de ce scénario à exécuter (par exemple, le scénario **Authentification**), comme suit :
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment. Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux. Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario. Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools. Pour plus d’informations sur la gestion des scénarios en cours d’exécution, voir <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation de stop pour le service de journalisation centralisée dans Lync Server 2013</A> et <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser –Duration pour définir la durée d’exécution d’un scénario. Vous pouvez également définir –Computers, une liste de noms complets d’ordinateurs séparés par une virgule ou –Pools, une liste de noms complets de pools séparés par une virgule sur lesquels vous souhaitez exécuter la journalisation.
    
    Vous démarrez une session de journalisation pour le scénario *UserReplicator* sur le pool « pool01.contoso.net ». Vous définissez également la durée de la session de journalisation à 8 heures. Pour cela, tapez :
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :
    
    ![Exécution de Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Exécution de Start-CsClsLogging.")
    
    Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

