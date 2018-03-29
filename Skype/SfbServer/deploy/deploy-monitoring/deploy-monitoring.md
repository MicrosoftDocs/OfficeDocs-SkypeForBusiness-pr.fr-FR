---
title: Déployer la surveillance dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Résumé : Découvrez comment déployer la surveillance dans Skype pour Business Server 2015.'
ms.openlocfilehash: a963db346f5d9f7904b43fc2032aa881295d1b77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-monitoring-in-skype-for-business-server-2015"></a>Déployer la surveillance dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment déployer la surveillance dans Skype pour Business Server 2015.
  
Vous implémenterez généralement les services de surveillance au sein de votre topologie en effectuant les deux étapes suivantes :
  
1. Activation de l’analyse en même temps permet de paramétrer un nouveau Skype pour un pool de serveurs d’entreprise. (Dans Skype pour Business Server 2015, surveillance est activée ou désactivée selon le pool par pool.) Notez que vous pouvez activer suivi de pool sans réellement la collecte des données de surveillance, un processus est expliqué dans la section de configuration de l’enregistrement des détails d’appel et les paramètres de qualité de l’expérience de cette documentation.
    
2. Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.
    
Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 ou Microsoft SQL Server 2014.
  
> [!NOTE]
> Si le contrôle a été activé pour un pool, vous pouvez désactiver le processus de collecte des données d’analyse sans avoir à modifier votre topologie : Skype pour Business Server fournit un moyen de désactiver (et alors réactiver ultérieurement) enregistrement de détail appels (CDR) ou qualité de Collecte de données d’expérience (QoE). Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document. 
  
Une autre amélioration importante à l’analyse dans Skype pour Business Server 2015 est le fait que Skype pour les rapports de surveillance Business Server prennent désormais en charge IPv6 : affichées dans les rapports qui utilisent le champ de l’adresse IP IPv4 ou une adresse IPv6 en fonction de : 1) le SQL requête utilisée ; et 2) où ou non l’adresse IPv6 est stocké dans la base de données de surveillance.
  
> [!NOTE]
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server. 
  
Cette documentation vous guide tout au long du processus d’installation et de configuration des rapports de surveillance et de contrôle pour Skype pour Business Server 2015. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :
  
- activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;
    
- Installer SQL Server Reporting Services et le Skype pour Business Server rapports d’analyse. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;
    
- configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données. D’enregistrement des données fournit un moyen d’effectuer le suivi de l’utilisation de Skype pour les fonctionnalités de Business Server tels que la voix sur IP (VoIP) pour les appels ; instant messaging (IM) ; transferts de fichiers ; audio/vidéo (A / V) de conférence ; et sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;
    
- vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.
    
## <a name="deployment-checklist-for-monitoring"></a>Liste de vérification du déploiement pour la surveillance

Bien que le contrôle est déjà installé et activé sur chaque serveur frontal, il existe toujours plusieurs étapes que vous devez entreprendre avant de pouvoir effectivement en cours pour collecter des données de surveillance de Skype pour Business Server 2015. Ces étapes sont décrites dans la liste de vérification suivante :
  
|**Phase de**|**Étapes**|**Appartenance au rôle et groupe**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.  <br/> |Utilisateur de domaine qui est également membre du groupe Administrateurs local.  <br/> |[Matériel pris en charge](http://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Logiciel de serveur et de la prise en charge de l’Infrastructure](http://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge la surveillance** <br/> |Skype d’utilisation pour le Générateur de topologies 2015 Business Server ajouter des bases de données de la topologie, de surveillance puis publiées la topologie mis à jour.  <br/> |Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.  <br/> Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.  <br/> |[Associer un pool frontal dans Skype pour Business Server 2015 dans un magasin de surveillance](associate-a-monitoring-store.md) <br/> |
|**Activer les paramètres de surveillance appropriés** <br/> |Activez l’enregistrement des détails des appels et/ou la surveillance QoE au niveau des étendues Globale et/ou Site.  <br/> |Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.  <br/> |[Configurer l’enregistrement détail des appels et des paramètres de qualité de l’expérience dans Skype pour Business Server 2015](call-detail-recording-and-qoe.md) <br/> |
   
## <a name="enable-monitoring"></a>Activer la surveillance

Bien que les agents de collection de données unifié sont automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commence automatiquement à collecter des données d’analyse au moment où que vous avez terminé l’installation Skype pour Business Server 2015. Auparavant, vous devez associer vos serveurs frontaux/pools frontaux à une base de données de surveillance et vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience au niveau de l’étendue globale et/ou de l’étendue du site.
  
Pour obtenir des instructions détaillées sur l’association de serveurs frontaux ou les pools de Front-End avec une analyse de la base de données, consultez la rubrique [associer une banque de surveillance avec un pool frontal dans Skype pour Business Server 2015](associate-a-monitoring-store.md) dans le guide de déploiement. Une fois ces associations effectuées, et après que votre nouveau Skype pour la topologie de serveur d’entreprise a été publié, vous toujours seront pas en mesure de collecter les données d’analyse. C’est parce que, par défaut, la collecte des données à la fois les CD-r et QoE est désactivée lorsque vous installez Skype pour Business Server 2015.
  
Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience. (Notez que vous n’avez pas à activer les deux CD-r et QoE monitoring ; si vous préférez, vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé.) Pour activer les CD-r de la surveillance, à l’exécution de la portée globale, la commande suivante dans la Skype pour Business Server Management Shell :
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Vous pouvez aussi activer le CDR surveillance à partir dans la Skype pour panneau de commande du serveur Business. À partir de dans la Skype pour le panneau de configuration de Business Server, procédez comme suit :
  
1. Cliquez sur **Surveillance**.
    
2. Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.
    
3. Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.
    
Pour permettre à la portée globale de surveillance QoE, exécutez cette commande à partir de la Skype pour Business Server Management Shell :
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si vous préférez, vous pouvez également activer QoE surveillance à partir dans la Skype pour le panneau de configuration de Business Server. Dans le Panneau de configuration, effectuez la procédure suivante :
  
1. Cliquez sur **Surveillance**.
    
2. Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.
    
3. Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.
    
Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation. Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site. Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin. Pour plus d’informations sur la gestion des paramètres de configuration de votre analyse, consultez la rubrique du guide de déploiement [d’enregistrement des données configuration et les paramètres de qualité d’expérience dans Skype pour Business Server 2015](call-detail-recording-and-qoe.md).
  

