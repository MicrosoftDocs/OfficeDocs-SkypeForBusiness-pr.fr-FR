---
title: Démarrer ou arrêter la capture du journal CLS dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Résumé : Découvrez comment démarrer ou arrêter une session de capture du journal du service de journalisation centralisée Skype Entreprise Server 2015.'
---

# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Démarrer ou arrêter la capture du journal CLS dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment démarrer ou arrêter une session de capture du journal du service de journalisation centralisée Skype Entreprise Server 2015.
  
Pour capturer les journaux de suivi à l’aide du service de journalisation centralisée, vous devez émettre une commande pour commencer la journalisation sur un ou plusieurs ordinateurs et pools. Vous devez également émettre des paramètres qui définissent les ordinateurs ou pools, les scénarios à exécuter (par exemple, AlwaysOn, un autre scénario prédéféré ou un scénario que vous avez créé), les composants Skype Entreprise Server (par exemple, S4, SipStack) à suivre.
  
Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat. Dans le service de journalisation centralisée, un scénario est le concept d’une connexion basée sur une collection de composants serveur, de niveaux de journalisation et d’indicateurs, ce qui est beaucoup plus efficace et utile que d’avoir à définir ces éléments par serveur. Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.
  
Le scénario par défaut est appelé **AlwaysOn**. Comme son nom l’indique, AlwaysOn est constamment exécuté. Le scénario AlwaysOn recueille des informations de niveau de journalisation Info (notez que le niveau de journalisation Info inclut les messages d’erreur fatale, d’erreur et d’avertissement en plus des messages Info) pour de nombreux composants serveur parmi les plus courants. AlwaysOn recueille des informations avant, pendant et après qu’un problème se produit. Ce comportement est considérablement différent du comportement type des anciens outils de journalisation tels qu’OCSLogger. Vous deviez en effet exécuter OCSLogger après qu’un problème se soit produit, ce qui rendait la résolution plus difficile, car les données dont vous disposiez étaient réactives et non proactives. Si AlwaysOn ne contient pas les informations que vous recherchez concernant le composant à l’origine du problème et vous indiquant la marche à suivre pour le résoudre (ce qui ne risque pas d’être le cas étant donnée les informations fournies par AlwaysOn), il fournit un niveau raisonnable d’informations pour déterminer les autres actions que vous devez effectuer, comme créer un nouveau scénario, recueillir d’autres informations, exécuter une autre recherche pour obtenir des détails plus précis, etc.
  
Le service de journalisation centralisée propose deux façons d’émettre des commandes. Plusieurs rubriques ont été axées sur l’utilisation de Windows PowerShell l’Skype Entreprise Server Management Shell. La possibilité d’utiliser un certain nombre de configurations et de commandes complexes favorise Windows PowerShell l’utilisation du service de journalisation centralisée. Étant donné Windows PowerShell’Skype Entreprise Server Management Shell est presque omniprésente pour toutes les fonctions dans Skype Entreprise Server, seules les commandes Windows PowerShell sont abordées. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Pour exécuter des Start-CsClsLogging avec des Windows PowerShell à l’aide de commandes de base

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
2. Démarrez un scénario de journalisation avec le service de journalisation centralisée en tapant ce qui suit :
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Par exemple, pour lancer le scénario **AlwaysOn**, tapez :
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Le scénario AlwaysOn n’a pas de durée par défaut. Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande **Stop-CsClsLogging**. Pour plus d’informations, voir [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps). Pour tous les autres scénarios, la durée par défaut est de 4 heures. 
  
3. Appuyez sur Entrée pour exécuter la commande. 
    
    > [!NOTE]
    > L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peut prendre quelques instants (de 30 à 60 secondes). 
  
     ![Exécution de Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging**, avec le nom de ce scénario à exécuter (par exemple, le scénario **Authentification**), comme suit :
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment. Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux. Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario. Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Pour exécuter des Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
2. Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser -Duration pour ajuster la durée d’utilisation du scénario. Vous pouvez également définir -Computers, une liste de noms de domaine complets (FQDN) d’ordinateurs séparés par une virgule, ou -Pools, une liste séparée par des virgules de noms de domaine complets pour les pools sur qui vous souhaitez exécuter la journalisation.
    
    Vous démarrez une session de journalisation pour le scénario UserReplicator sur le pool « pool01.contoso.net ». Vous définissez également la durée de la session de journalisation à 8 heures. Pour cela, tapez :
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :
    
     ![Exécution de Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Arrêter la capture du journal du service de journalisation centralisée
<a name="stop"> </a>

Vous pouvez arrêter une session de journalisation en cours avec l’applet de commande Stop-CsClsLogging. En règle générale, il n’existe pas beaucoup de situations dans lesquelles vous devez arrêter une session de journalisation. Par exemple, vous pouvez faire des recherches dans les journaux et modifier des configurations sans devoir arrêter d’abord la journalisation. Si deux scénarios sont en cours d’exécution, par exemple AlwaysOn et UserReplicator, alors que vous devez recueillir des informations relatives à l’authentification, vous devez arrêter un de ces deux scénarios (au niveau global, du site, du pool ou de l’ordinateur) avant de pouvoir lancer l’exécution du scénario  d’authentification. Pour plus d’informations, voir [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Lorsque vous déterminez les scénarios que vous pouvez exécuter sur un déploiement, un pool ou un ordinateur donné, vous devez vous souvenir que vous êtes limité à l’exécution de deux **scénarios par** ordinateur : AlwaysOn et un scénario personnalisé. Si vous procédez à la journalisation de l’activité d’un pool, vous devez traiter ce pool globalement. Dans la plupart des cas, il n’est pas judicieux d’exécuter différents scénarios sur chaque ordinateur dans un pool. Il n’est pas non plus logique d’examiner le problème pour lequel vous recherchez des données et vous demander alors quel scénario convient le mieux pour un ordinateur donné dans le déploiement entier. Par exemple, si vous envisagez le scénario UserReplicator, l’exécution de UserReplicator sur un serveur Edge ou un pool de serveurs Edge ne serait pas très importante. 
  
Une fois que vous avez compris l’origine du problème et avez déterminé son impact, vous devez choisir soigneusement les scénarios à exécuter sur quels ordinateurs et pools. Bien qu’il soit judicieux d’exécuter le scénario AlwaysOn pour une application large, car il recueille des informations sur une grande variété de fournisseurs, certains scénarios ne sont utiles que sur certains ordinateurs ou pools. De plus, lorsque vous lancez une session de journalisation vous devez choisir au préalable le scénario offrant les meilleurs résultats. Si vous utilisez un scénario inapproprié, ou si vous utilisez un scénario qui est approprié pour la tâche mais pas adapté au niveau d’application envisagé (global, site, pool ou ordinateur), vous risquez d’obtenir des données inutiles, comme si vous n’aviez pas exécuté de scénario du tout.
  
Pour contrôler les fonctions du service de journalisation centralisée à l’aide de l’environnement de ligne de commande Skype Entreprise Server Management Shell, vous devez être membre des groupes de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes. Pour retourner la liste de tous les rôles RBAC attribués à cette cmdlet (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Skype Entreprise Server Management Shell ou Windows PowerShell suivante :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Par exemple :
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Vous vous demandez peut-être : maintenant que vous avez activé la journalisation, où sont conservés les journaux ? Étant donné que vous accéderez aux informations stockées dans les journaux à l’aide de requêtes de l’shell de gestion envoyées aux agents CLS, et que vous pouvez obtenir les résultats dans plusieurs formats de fichiers possibles, où, sur chaque serveur, un agent CLS conserve ses enregistrements n’est pas vraiment important à connaître.  Les fichiers journaux peuvent être enregistrés à un emplacement que vous spécifiez, que vous lisez et analysez à l’aide de divers outils, notamment **Snooper.exe** et tout outil qui peut lire un fichier texte, tel que **Notepad.exe**. Snooper.exe fait partie des outils de débogage Skype Entreprise Server 2015 et est disponible en téléchargement [Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Pour arrêter une session du service de journalisation centralisée en cours d’exécution

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
2. Interrogez le service de journalisation centralisée pour connaître les scénarios en cours d’exécution en tapant les données suivantes :
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell console après avoir appelé Show-CsCl.](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Le résultat de Show-CsClsLogging est un résumé des scénarios en cours d’exécution et de leur étendue d’application. Pour plus d’informations, voir [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Pour arrêter une session de journalisation en cours avec un scénario spécifique, tapez :
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Par exemple :
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Cette commande arrête la journalisation avec le scénario UserReplicatior sur pool01.contoso.net.
    
    > [!NOTE]
    > Les journaux créés au cours de cette session de journalisation avec le scénario UserReplicator ne sont pas supprimés. Vous pouvez continuer à effectuer des recherches avec la journalisation au lieu d’utiliser la commande Search-CsClsLogging. Pour plus d’informations, voir [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Faisant pendant à l’applet de commande Start-CsClsLogging, l’applet de commande Stop-CsClsLogging arrête la session de journalisation, définie par des scénarios, et conserve les journaux créés par celle-ci. Vous pouvez exécuter deux scénarios sur un ordinateur donné à tout moment. La méthode d’arrêt d’un scénario pour recueillir des informations à l’aide d’un autre scénario est une tâche courante que vous pouvez effectuer au cours du dépannage de la plupart des charges de travail.
## <a name="see-also"></a>Voir aussi
<a name="stop"> </a>

[Service de journalisation centralisée Skype Entreprise 2015](centralized-logging-service.md)