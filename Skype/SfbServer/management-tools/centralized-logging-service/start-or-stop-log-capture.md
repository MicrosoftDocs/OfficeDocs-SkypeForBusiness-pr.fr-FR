---
title: Début ou arrêt de la capture dʼun journal CLS dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Résumé : Découvrez comment démarrer ou arrêter une session de capture des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: c0b65fddcb5036cf41866ce79d82ae0bc49a79e3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373763"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Début ou arrêt de la capture dʼun journal CLS dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment démarrer ou arrêter une session de capture des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.
  
Pour capturer des journaux de suivi à l’aide du Service de journalisation centralisée, vous exécutez une commande pour lancer la consignation sur un ou plusieurs ordinateurs et pools. Vous exécutez également les paramètres qui définissent les ordinateurs ou les pools, quels scénarios à exécuter (par exemple, AlwaysOn, un autre scénario prédéfini ou un scénario que vous avez créé), quel Skype pour les composants Business Server (par exemple, S4, SipStack) pour le suivi.
  
Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat. Dans le Service de journalisation centralisée, un scénario est le concept d’activation de la journalisation basé sur une collection de composants du serveur, les niveaux de journalisation et les indicateurs, qui est beaucoup plus efficace et utile plutôt que de définir les éléments suivants sur chaque serveur. Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.
  
Le scénario par défaut s’appelle **AlwaysOn**. Comme son nom l’indique, AlwaysOn a pour objectif d’exécuter le scénario de manière constante. Le scénario AlwaysOn collecte des informations (notez que le niveau de journalisation des messages Info comprend, en plus des messages Info, les messages Error, Fatal et Warning) concernant bon nombre des composants serveur les plus courants. AlwaysOn collecte des informations avant, pendant et après la survenue d’un problème, comportement totalement différent des précédents outils de journalisation, tels que OCSLogger. Auparavant, vous exécutiez OCSLogger une fois le problème survenu, ce qui compliquait davantage la résolution des erreurs, car les données dont vous disposiez étaient réactives, et non pas proactives. Si AlwaysOn ne contient pas les informations que vous cherchez pour identifier le composant qui pose problème et d’indiquer la procédure corrective appropriée (ce qui est peu probable, étant donné l’ampleur et la profondeur des fournisseurs dans AlwaysOn), il indiquera un niveau raisonnable d’informations permettant de déterminer les autres opérations requises, par exemple créer un scénario, collecter d’autres informations, lancer une recherche différente afin de collecter des informations plus détaillées, etc.
  
Le Service de journalisation centralisée fournit deux méthodes pour envoyer des commandes. Un nombre de rubriques ont été axé sur l’utilisation de Windows PowerShell par le biais de la Skype pour Business Server Management Shell. La possibilité d’utiliser un nombre de commandes et des configurations complexes favorise Windows PowerShell pour l’utilisation du Service de journalisation centralisée. Étant donné que Windows PowerShell par le biais de la Skype pour Business Server Management Shell est presque omniprésent pour toutes les fonctions de Skype pour Business Server, seules les commandes de Windows PowerShell sont traitées. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide des commandes de base

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Démarrer un scénario de journalisation avec le Service de journalisation centralisée en tapant ce qui suit :
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Pour lancer le scénario **AlwaysOn**, par exemple, tapez :
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Le scénario AlwaysOn n’a pas de durée par défaut. Ce scénario s’exécute jusqu'à ce que vous l’interrompiez explicitement avec l’applet de commande **Stop-CsClsLogging** . Pour plus d’informations, voir [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Pour tous les autres scénarios, la durée par défaut est de 4 heures. 
  
3. Appuyez sur Entrée pour exécuter la commande. 
    
    > [!NOTE]
    > L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peuvent prendre quelques instants (de 30 à 60 secondes). 
  
     ![Exécution de Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging** avec le nom de ce scénario à exécuter comme suit (par exemple, le scénario **authentification**) :
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment. Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux. Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario. Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser - durée pour régler la durée pendant laquelle le scénario à exécuter. Vous pouvez également définir - ordinateurs, une liste de noms de domaine d’ordinateur pleinement qualifié (FQDN) séparés par une virgule, ou - liste des noms de domaine complets des pools que vous souhaitez exécuter ouverture de session séparés par des Pools, une virgule.
    
    Vous démarrez une session de journalisation pour le scénario UserReplicator sur le pool « pool01.contoso.net ». Vous définissez également la durée de la session de journalisation à 8 heures. Pour cela, tapez :
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :
    
     ![Exécution de Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Arrêter la capture du journal du Service de journalisation centralisée
<a name="stop"> </a>

Vous pouvez arrêter une session de journalisation en cours à l’aide de l’applet de commande Stop-CsClsLogging. En règle générale, il n’existe pas de nombreuses situations dans lesquelles vous devrez arrêter une session de journalisation. Par exemple, vous n’avez pas à arrêter une séance de journalisation pour effectuer une recherche dans les journaux ou modifier les paramètres. Si deux scénarios sont en cours d’exécution, par exemple AlwaysOn et UserReplicator, alors que vous devez recueillir des informations relatives à l’authentification, vous devez arrêter un de ces deux scénarios (au niveau global, du site, du pool ou de l’ordinateur) avant de pouvoir lancer l’exécution du scénario Authentication. Pour plus d’informations, voir [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Lorsque vous souhaitez déterminer les scénarios que vous pouvez exécuter sur un déploiement, un pool ou un ordinateur donné, gardez à l’esprit que vous ne pouvez exécuter plus de deux scénarios **par ordinateur** : AlwaysOn et un scénario personnalisé. Si vous effectuez la journalisation de l’activité d’un pool, vous devrez considérer ce pool globalement. Dans la plupart des cas, il n’est pas judicieux d’exécuter différents scénarios sur chaque ordinateur dans un pool. Il n’est pas non plus logique d’examiner le problème pour lequel vous recherchez des données et vous demander alors quel scénario convient le mieux pour un ordinateur donné dans le déploiement entier. Par exemple, si vous considérez le scénario UserReplicator, il est très peu valeur dans UserReplicator en cours d’exécution sur un serveur Edge ou pool de serveurs Edge. 
  
Une fois que vous avez compris l’origine du problème et avez déterminé son impact, vous devez choisir soigneusement les scénarios à exécuter sur quels ordinateurs et pools. Bien qu’il soit judicieux d’exécuter le scénario AlwaysOn pour une application large, car il recueille des informations sur une grande variété de fournisseurs, certains scénarios ne sont utiles que sur certains ordinateurs ou pools. De plus, lorsque vous lancez une session de journalisation vous devez choisir au préalable le scénario offrant les meilleurs résultats. Si vous utilisez un scénario inapproprié, ou si vous utilisez un scénario qui est approprié pour la tâche mais pas adapté au niveau d’application envisagé (global, site, pool ou ordinateur), vous risquez d’obtenir des données inutiles, comme si vous n’aviez pas exécuté de scénario du tout.
  
Pour contrôler les fonctions de Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes. Pour retourner une liste de tous les rôles RBAC que cette applet de commande a été assigné à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Pour arrêter une session de Service de journalisation centralisée actuellement en cours d’exécution

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Requête the Centralized Logging Service permettant de savoir quel scénarios sont en cours d’exécution en tapant la commande suivante :
    
   ```
   Show-CsClsLogging
   ```

   ![Console Windows PowerShell après appel de Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging affiche une synthèse des scénarios en cours d’exécution et de leur étendue d’application. Pour plus d’informations, voir [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Pour arrêter une session de journalisation en cours avec un scénario spécifique, tapez :
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Exemple :
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Cette commande arrête la journalisation avec le scénario UserReplicatior sur pool01.contoso.net.
    
    > [!NOTE]
    > Les journaux créés au cours de cette session de journalisation à l’aide du scénario UserReplicator sont conservés. Vous pouvez continuer à effectuer des recherches avec la journalisation à l’aide de la commande Search-CsClsLogging. Pour plus d’informations, consultez la rubrique [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Faisant pendant à l’applet de commande Start-CsClsLogging, l’applet de commande Stop-CsClsLogging arrête la session de journalisation, définie par des scénarios, et conserve les journaux créés par celle-ci. Vous pouvez exécuter deux scénarios sur un ordinateur donné à tout moment. La méthode d’arrêt d’un scénario pour recueillir des informations à l’aide d’un autre scénario est une tâche courante que vous pouvez effectuer au cours du dépannage de la plupart des charges de travail.
## <a name="see-also"></a>Voir aussi
<a name="stop"> </a>

[Service de journalisation centralisée pour Skype Entreprise 2015](centralized-logging-service.md)