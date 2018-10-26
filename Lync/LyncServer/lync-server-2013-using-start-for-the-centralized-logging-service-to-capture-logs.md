---
title: "Ut. comm. Start pour capture des journaux par le serv. de journ. centralisée"
TOCtitle: "Ut. comm. Start pour capture des journaux par le serv. de journ. centralisée"
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49891218
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la commande Start pour la capture des journaux par le service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2013-02-21_

Pour obtenir des journaux de suivi à l’aide du service de journalisation centralisée, vous devez exécuter une commande pour lancer la journalisation sur des ordinateurs et des pools. Vous devez également configurer des paramètres qui définissent quels scénarios à exécuter sur quels ordinateurs ou pools (par exemple, AlwaysOn, un autre scénario prédéfini ou un scénario que vous avez créé), et quels composants de Lync Server (par exemple, S4, SipStack) doivent faire l’objet d’un suivi.

Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat. Dans le service de journalisation centralisée, un scénario est le concept activant la journalisation à partir d’un ensemble de composants serveur, de niveaux de journalisation et d’indicateurs, ce qui est plus efficace et pratique que de devoir définir ces éléments par serveur. Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.

Le scénario par défaut est appelé **AlwaysOn**. Comme son nom l’indique, AlwaysOn est constamment exécuté. Le scénario AlwaysOn recueille des informations de niveau de journalisation Info (notez que le niveau de journalisation Info inclut les messages d’erreur fatale, d’erreur et d’avertissement en plus des messages Info) pour de nombreux composants serveur parmi les plus courants. AlwaysOn recueille des informations avant, pendant et après qu’un problème se produit. Ce comportement est considérablement différent du comportement type des anciens outils de journalisation tels qu’OCSLogger. Vous deviez en effet exécuter OCSLogger après qu’un problème se soit produit, ce qui rendait la résolution plus difficile, car les données dont vous disposiez étaient réactives et non proactives. Si AlwaysOn ne contient pas les informations que vous recherchez concernant le composant à l’origine du problème et vous indiquant la marche à suivre pour le résoudre (ce qui ne risque pas d’être le cas étant donnée les informations fournies par AlwaysOn), il fournit un niveau raisonnable d’informations pour déterminer les autres actions que vous devez effectuer, comme créer un nouveau scénario, recueillir d’autres informations, exécuter une autre recherche pour obtenir des détails plus précis, etc.

Le service de journalisation centralisée permet d’exécuter des commandes de deux manières. Un certain nombre de rubriques ont été consacrées à l’utilisation de Windows PowerShell via Lync Server Management Shell. De par sa capacité à utiliser un certain nombre de configurations et de commandes complexes, il est recommandé d’utiliser Windows PowerShell pour le service de journalisation centralisée. Étant donné que Windows PowerShell via Lync Server Management Shell couvre presque toutes les fonctions de Lync Server, seules les commandes Windows PowerShell sont présentées ici.

> [!NOTE]  
> Si vous décidez d’utiliser l’ensemble limité de commandes disponibles à partir de la ligne de commande, vous pouvez obtenir de l’aide avec CLSController.exe. Il vous suffit pour cela de taper <code>ClsController.exe</code>. Par défaut, <strong>ClsController.exe</strong> est installé dans le répertoire C:\Program Files\Microsoft Lync Server 2013\ClsAgent.

## Pour exécuter Start-CsClsLogging avec Windows PowerShell en utilisant des commandes de base

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Lancez un scénario de journalisation avec le service de journalisation centralisée en tapant ce qui suit :
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Par exemple, pour lancer le scénario **AlwaysOn**, tapez :
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    > [!NOTE]  
    > Le scénario AlwaysOn n’a pas de durée par défaut. Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande <strong>Stop-CsClsLogging</strong>. Pour plus d’informations, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>. Pour tous les autres scénarios, la durée par défaut est de 4 heures.

3.  Appuyez sur Entrée pour exécuter la commande.
    
    > [!NOTE]  
    > L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peut prendre quelques instants (de 30 à 60 secondes).    
    ![Exécution de Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Exécution de Start-CsClsLogging.")

4.  Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging**, avec le nom de ce scénario à exécuter (par exemple, le scénario **Authentification**), comme suit :
    
        Start-CsClsLogging -Scenario Authentication
    
    > [!IMPORTANT]  
    > Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment. Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux. Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario. Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools. Pour plus d’informations sur la gestion des scénarios en cours d’exécution, consultez les rubriques <a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Utilisation de la commande Stop pour le service de journalisation centralisée</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>.

## Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser –Duration pour définir la durée d’exécution d’un scénario. Vous pouvez également définir –Computers, une liste de noms complets d’ordinateurs séparés par une virgule ou –Pools, une liste de noms complets de pools séparés par une virgule sur lesquels vous souhaitez exécuter la journalisation.
    
    Pour lancer une session de journalisation pour le scénario *UserReplicator* sur le pool “pool01.contoso.net” avec une durée de 8 heures, tapez :
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :
    
    ![Exécution de Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Exécution de Start-CsClsLogging.")
    
    Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés.

## Voir aussi

#### Concepts

[Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)

