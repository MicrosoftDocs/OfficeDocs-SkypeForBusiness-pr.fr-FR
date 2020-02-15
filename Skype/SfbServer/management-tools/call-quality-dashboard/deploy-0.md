---
title: Déployer le tableau de bord de qualité des appels pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : Découvrez le processus de déploiement du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: d42d735ab5a60ec02ad2e1f4f696908996457c0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042261"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Déployer le tableau de bord de qualité des appels pour Skype entreprise Server
 
**Résumé :** Découvrez le processus de déploiement du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
## <a name="deployment-overview"></a>Présentation du déploiement

Le tableau de bord de qualité des appels (CQD) se compose de trois composants principaux :
  
- **Base de données d’archivage**, dans laquelle les données de qualité de l’expérience (QoE) sont répliquées et stockées.
    
- **Cube**, où les données de la base de données d’archivage QoE sont regroupées pour un accès optimisé et rapide.
    
- **Portail**, où les utilisateurs peuvent facilement interroger et visualiser les données QoE.
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Le processus de configuration de l’archive QoE implique la création de la base de données d’archivage QoE, le déploiement d’une procédure stockée SQL Server qui déplace les données de la base de données de mesures QoE source vers la base de données d’archivage QoE et la configuration du travail de l’agent SQL Server pour l’exécution de l’enregistrement procédure à intervalles réguliers. 
  
Déploiement de cube obtient des informations de l’utilisateur sur l’emplacement où se trouve l’archive QoE, déploie le cube et configure un travail d’agent SQL Server régulier qui actualisera le cube à intervalles réguliers.
  
L’installation du portail crée une base de données de référentiel qui stocke le mappage des utilisateurs CQD sur les rapports/requêtes de chaque utilisateur. Il configure ensuite une application Web IIS qui est le tableau de bord dans lequel les utilisateurs peuvent afficher un ensemble prédéfini de rapports, ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données à partir du cube. L’installation du portail crée deux applications Web supplémentaires qui exposent les API permettant aux utilisateurs d’accéder par programme au référentiel et au cube. (Ces API sont également utilisées en interne par le tableau de bord.)
  

|**Étape**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|Installez le matériel et les logiciels prérequis.  <br/> |Déterminez la configuration de CQD, puis choisissez un serveur SQL Server à partir duquel effectuer l’installation.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Section « conditions préalables à l’installation » dans la documentation de déploiement.  <br/> |
|Installez CQD.  <br/> |Exécutez le fichier MSI en suivant le document de déploiement.  <br/> |Pour effectuer la configuration, le compte d’installation doit être un utilisateur de domaine membre du groupe Administrateurs local et disposer d’un accès en lecture à la base de données des mesures QoE sur le serveur de surveillance.  <br/> |Sections « comptes et étapes de déploiement » dans la documentation de déploiement.  <br/> |
|Accorder l’accès utilisateur.  <br/> |Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7,0. Pour plus d’informations, consultez la rubrique [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Managing User Access for the Portal section dans la documentation de déploiement.  <br/> |
|Facultatif : fournissez les informations de mappage de sous-réseau.  <br/> |Remplissez le réseau et créez des tables de mappage dans la base de données d’archivage QoE.  <br/> |Un compte avec un accès en écriture à la base de données d’archivage QoE.  <br/> |Section « fourniture des informations de sous-réseau » dans la documentation utilisateur.  <br/> |
   


Le déploiement du tableau de bord de qualité des appels implique la configuration de l’infrastructure et l’installation du logiciel. La procédure suivante décrit le processus.
  
## <a name="deployment-steps"></a>Étapes de déploiement

1. Copiez le CallQualityDashboard. msi sur l’ordinateur sur lequel le composant de base de données d’archivage de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server est installé). 
    
2. Exécutez le MSI (Windows invite à s’exécuter avec les privilèges d’administrateur). 
    
3. Acceptez le CLUF.
    
4. Sélectionnez le dossier de destination où les fichiers associés aux composants de tableau de bord de qualité des appels seront localisés ou accepteront l’emplacement par défaut.
    
5. Sélectionnez toutes les fonctionnalités.
    
6. Sur la page Configuration de l’archive QoE, fournissez les informations suivantes :
    
   - Valeurs **QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données de mesures QoE (il s’agit de la source de données).
    
   - **Nom de serveur SQL de l’archive QoE :** Ce champ est en lecture seule et correspond au nom de domaine complet de l’ordinateur local. La base de données d’archivage ne peut être installée que sur l’ordinateur local.
    
   - **Instance de serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server locale pour laquelle la base de données d’archivage doit être créée. Pour utiliser une instance SQL Server par défaut, laissez ce champ vide. Pour utiliser une instance SQL Server nommée, spécifiez le nom de l’instance (par exemple, le\"nom qui suit ").
    
   - **Base de données d’archivage QoE :** Par défaut, cette option est définie sur « créer une nouvelle base de données ». Étant donné que la mise à niveau de la base de données d’archivage n’est pas prise en charge, le seul cas où l’option « utiliser une base de données existante » peut être utilisée est si la base de données d’archivage existante a le même schéma que la build à installer.
    
   - **Répertoire du fichier de base de données :** Chemin d’accès à l’emplacement des fichiers de base de données (. mdf et. ldf) de la base de données d’archivage. Il doit se trouver sur un lecteur (HDD2 dans la configuration matérielle recommandée) distinct du système d’exploitation. Notez que, étant donné que les noms de fichier sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichiers.
    
   - **Utiliser plusieurs partitions :** La valeur par défaut est « multiple partition », ce qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server. Pour Standard Edition, sélectionnez l’option « partition unique ». Notez que les performances de traitement de cube peuvent être affectées si une seule partition est utilisée.
    
     > [!NOTE]
     > La sélection de l’option utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée. Pour le modifier, la fonctionnalité de cube doit être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration. 
  
   - **Répertoire du fichier de partition :** Chemin d’accès à l’emplacement où les partitions de la base de données d’archivage QoE doivent être placées. Il doit se trouver sur un lecteur (HDD3 dans la configuration matérielle recommandée) distinct du lecteur du système d’exploitation et du lecteur des fichiers journaux de base de données SQL. Notez que, étant donné que les noms de fichier sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichiers.
    
   - **Utilisateur du travail de l’agent SQL &amp; -mot de passe du nom d’utilisateur :** Nom de compte de service de domaine et mot de passe (masqué) qui sera utilisé pour exécuter l’étape « données d’archivage QoE » du travail de l’agent SQL Server (qui exécutera la procédure stockée pour extraire les données de la base de données de valeurs QoE dans la base de données d’archivage, de sorte que ce compte doit disposer d’un accès en lecture à la base de Ce compte doit également disposer d’une connexion dans l’instance de SQL Server d’archive QoE).
    
     > [!NOTE]
     > Le compte sous lequel l’instance SQL Server est en cours d’exécution, tel que NT SERVICE\MSSQLSERVER, doit disposer d’une autorisation ou d’un accès aux annuaires ci-dessus pour que l’installation réussisse. Pour plus d’informations, voir [configurer les autorisations du système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. Lorsque vous cliquez sur suivant, le programme d’installation effectue des vérifications préalables et un rapport si des problèmes sont détectés. Lorsque toutes les vérifications de conditions préalables sont réussies, le programme d’installation accède à la page Configuration du cube. 
    
    > [!NOTE]
    > Si le programme d’installation affiche un message d’avertissement indiquant que le service SQL Server Agent pour l’instance SQL Server d’archive QoE n’est pas en cours d’exécution, l’installation peut se poursuivre, mais après l’installation, vérifiez que le service Agent SQL est en cours d’exécution et définissez le type de démarrage sur Automatique afin que la tâche planifiée s’exécute. 
  
8. Sur la page Configuration du cube, fournissez les informations suivantes :
    
   - **Nom de serveur SQL de l’archive QoE :** Ce champ est en lecture seule et correspond au nom de domaine complet de l’ordinateur local. Le cube ne peut être installé qu’à partir de l’ordinateur disposant d’une base de données d’archivage QoE (Remarque. Le cube lui-même peut être installé sur un ordinateur distant. Voir ci-dessous)
    
   - **Instance de serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données d’archive QoE. Pour spécifier une instance SQL Server par défaut, laissez ce champ vide. Pour spécifier une instance nommée de SQL Server, entrez le nom de l’instance (par exemple, le\"nom qui suit "). Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.
    
   - **Serveur d’analyse de cube :** Nom de l’instance du service SQL Server Analysis pour lequel le cube doit être créé. Il peut s’agir d’un autre ordinateur, mais l’utilisateur qui provient de l’installation doit être membre des administrateurs de serveur de l’instance SQL Server Analysis service cible.
    
     > [!NOTE]
     >  Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, consultez la rubrique [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx) .
  
   - **Utiliser plusieurs partitions :** La valeur par défaut est « multiple partition », ce qui nécessite Business Intelligence Edition ou Enterprise Edition de SQL Server. Pour Standard Edition, sélectionnez l’option « partition unique ». Notez que les performances de traitement de cube peuvent être affectées si une seule partition est utilisée.
    
     > [!NOTE]
     >  La sélection de l’option utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée. Pour le modifier, la fonctionnalité de cube doit être désinstallée, puis réinstallée à l’aide de l’option « modifier » dans le panneau de configuration.
  
   - **Cube user-nom &amp; d’utilisateur mot de passe :** Nom et mot de passe du compte de service de domaine (masqué) qui déclencheront le traitement du cube. Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie sur la page Configuration de l’Archive pour l’utilisateur du travail de l’agent SQL, mais nous vous recommandons de spécifier un autre compte de service de domaine afin que le programme d’installation puisse accorder au privilège le moins requis.
    
9. Lorsque vous cliquez sur suivant, une autre série de validations est effectuée et tout problème est signalé. Une fois la validation terminée, le programme d’installation accède à la page Configuration du portail. 
    
10. Sur la page Configuration du portail, fournissez les informations suivantes :
    
    - **Serveur d’archive QoE SQL Server :** Nom de l’instance SQL Server où se trouve la base de données d’archivage QoE. Notez que contrairement à la page Configuration de l’archive QoE et la page Configuration du cube, le nom de l’ordinateur n’est pas fixe et doit être fourni. Si le composant d’archive QoE a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.
    
    - **Serveur d’analyse de cube :** Nom de l’instance du service SQL Server Analysis pour lequel se trouve le cube. Si le composant de cube a été sélectionné pour l’installation, ce champ est pré-rempli avec la valeur fournie sur la page Configuration du cube.
    
    - **Référentiel SQL Server :** Nom de l’instance SQL Server dans laquelle la base de données de référentiel doit être créée. Si le nom de l’instance SQL Server correspondant à l’emplacement de la base de données d’archivage QoE a été précédemment fourni dans le programme d’installation (dans les autres composants), ce champ sera pré-rempli avec le nom d’instance SQL Server de la base de données d’archive QoE. Il peut s’agir de n’importe quelle instance de SQL Server.
    
    - **Base de données de référentiel :** Par défaut, l’option est définie sur « créer une nouvelle base de données ». Étant donné que la mise à niveau de la base de données du référentiel n’est pas prise en charge, le seul cas où l’option « utiliser une base de données existante » peut être utilisée est si la base de données de référentiel existante a le même schéma que la build à installer.
    
    - **Utilisateur du pool d’applications IIS- &amp; mot de passe du nom d’utilisateur :** Compte sous lequel le pool d’applications IIS doit s’exécuter. Les champs nom d’utilisateur et mot de passe sont grisés si les comptes système prédéfinis sont sélectionnés. Ces champs seront uniquement activés si l’option « autres » est sélectionnée dans la zone de liste déroulante pour permettre à l’utilisateur d’entrer les informations de compte de service de domaine.
    
11. Lorsque vous cliquez sur suivant, le dernier cycle de validation est effectué afin de s’assurer que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et qu’IIS est disponible sur l’ordinateur. Une fois la validation terminée, le programme d’installation procède à la configuration. 
    
Lorsque le programme d’installation est exécuté, le plus probablement le travail de l’agent SQL Server est en cours, ce qui entraîne le chargement initial des données QoE et du traitement du cube. En fonction de la quantité de données dans QoE, le portail ne disposera pas de données disponibles pour l’affichage. Pour vérifier l’état du chargement des données et du traitement des cubes, `http://<machinename>/CQD/#/Health`accédez à. 
> [!NOTE]
> Notez que l’URL permettant de vérifier l’état du traitement de téléchargement de cube est sensible à la casse. Si vous entrez « Health », l’URL ne fonctionnera pas. Vous devez entrer « Health » à la fin de l’URL par un H majuscule. 
  
Les messages de journal détaillés s’affichent si le mode de débogage est activé. Pour activer le mode débogage, accédez à **%systemdrive%\Program Files\Skype for Business 2015 CQD\QoEDataService\web.config**et mettez à jour la ligne suivante de sorte que la valeur soit définie sur **true**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La page principale du portail est accessible `http://<machinename>/CQD`via. 
## <a name="managing-user-access-for-the-portal"></a>Gestion de l’accès des utilisateurs pour le portail

Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7,0. Pour plus d’informations sur la sécurité IIS, consultez la rubrique [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Tout site Web ou application Web hérite de l’autorisation d’URL par défaut configurée pour l’ensemble des services Internet (IIS), ce qui est généralement « autoriser tous les utilisateurs ». Si l’accès au portail doit être plus restrictif, les administrateurs peuvent accorder l’accès uniquement à un groupe spécifique d’utilisateurs en modifiant les « règles d’autorisation ».
  
![Déployer les règles d’autorisation de qualité des appels dans les services Internet (IIS)](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L’icône des règles d’autorisation ne doit pas être confondue avec le « .NET Authorization » dans la section ASP.NET, qui est un autre mécanisme d’autorisation. 
  
Les administrateurs doivent d’abord supprimer la règle « autoriser tous les utilisateurs » héritée. Cela empêche les utilisateurs non autorisés d’accéder au portail.
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Ensuite, les administrateurs doivent ajouter de nouvelles règles d’autorisation et accorder à des utilisateurs spécifiques l’autorisation d’accéder au portail. Il est recommandé de créer un groupe local appelé « CQDPortalUsers » pour gérer les utilisateurs.
  
![Déployer le tableau de bord de qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Les détails de la configuration sont stockés dans le fichier Web. config situé dans le répertoire physique du portail.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

L’étape suivante consiste à configurer le tableau de bord du CQD. Une fois que les utilisateurs sont authentifiés par les services Internet (IIS), ils doivent disposer d’autorisations de fichier dans le répertoire CQD pour accéder au contenu du portail Web. Il est possible de modifier les listes de Contrã’le d’accès par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs ou des groupes individuels ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichier intactes. Au lieu de cela, modifiez le paramètre IIS de manière à utiliser le processus de travail IIS pour accéder au répertoire CQD, quel que soit l’utilisateur authentifié. 
  
> [!IMPORTANT]
> Il est important de modifier uniquement ce paramètre pour l’application CQD, et non pour les deux applications API : QoEDataService et QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuration de l’accès au fichier pour le CQD (tableau de bord)

1. Ouvrez l’éditeur de configuration pour CQD.
    
     ![Déployer le tableau de bord de qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Sous section, choisissez **System. webServer/ServerRuntime**.
    
     ![Déployer le tableau de bord de qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.
    
     ![Déployer le tableau de bord de qualité des appels-éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Cliquez sur **appliquer** dans la partie droite de la page.
    
## <a name="known-issues"></a>Problèmes connus

### <a name="the-cqd-shows-no-data-after-deployment"></a>Le CQD n’affiche aucune donnée après le déploiement

Le message d’erreur suivant peut s’afficher :

*Nous n’avons pas pu exécuter la requête pendant son exécution sur le cube. Utilisez l’éditeur de requête pour modifier la requête et résoudre les problèmes. Assurez-vous également que le cube est accessible.*

Cela signifie que le cube doit être traité dans SQL Server Analysis Services avant d’être utilisé dans CQD. Vous pouvez résoudre ce processus en procédant comme suit :

1. Ouvrez SQL Management Studio et sélectionnez **Analysis Services**.

2. Développez l’objet **QoECube** , sélectionnez la **mesure QoE**, cliquez avec le bouton droit, puis cliquez sur **Parcourir**. 

    Si cette valeur renvoie un navigateur vide, le cube n’a pas encore été exécuté.

3. Cliquez avec le bouton droit sur **QoE Metric** angain et choisissez **Process**.

4. Une fois le traitement terminé, cliquez à nouveau avec le bouton droit sur l’objet, puis choisissez **Parcourir** pour confirmer que la page du navigateur affiche maintenant des données. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Les utilisateurs ont des difficultés à se connecter car le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS

Dans de rares cas, le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS. La modification manuelle est requise pour permettre aux utilisateurs de se connecter à CQD. Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :
  
1. Ouvrez le gestionnaire des services Internet (IIS), puis accédez au site Web par défaut.
    
     ![Déployer le tableau de bord de qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Cliquez sur « authentification ». Si les options « authentification anonyme », « emprunt d’identité ASP.NET », « authentification de formulaire » et « authentification Windows » ne correspondent pas aux paramètres indiqués ci-dessous, modifiez-les manuellement pour qu’ils correspondent aux paramètres ci-dessous. Tous les autres mécanismes d’authentification doivent être désactivés.
    
     ![Déployer le tableau de bord de qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Pour « authentification Windows », cliquez sur Paramètres avancés dans la partie droite.
    
     ![Déployer le tableau de bord de qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Définissez « protection étendue » pour accepter et activer la case à cocher « Activer l’authentification en mode noyau ».
    
     ![Déployer le tableau de bord de qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Répétez les étapes ci-dessus pour chacune des entrées « CQD », « QoEDataService » et « QoERepositoryService » en dessous de « Default Web site ».
    
Pour les liaisons de ports HTTP et HTTPs, le programme d’installation crée des liaisons de ports sur les numéros de port par défaut (port 80 pour HTTP et port 443 pour HTTPs). S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et le comportement des services Internet (IIS) ne peut pas être prédit. La meilleure façon d’éviter ce problème est de s’assurer qu’aucun autre site Web n’est mappé sur les ports 80 et 443 avant l’installation de CQD. 
  
Pour activer SSL/TLS dans les services Internet (IIS) et obliger les utilisateurs à se connecter via HTTPs sécurisé au lieu de HTTP :
  
1. Configure Secure Sockets Layer dans les services Internet (IIS), consultez la rubrique [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx). Une fois terminée, `http` remplacez `https`par.
    
2. Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, consultez [la rubrique How to Enable SSL encryption for an instance of SQL Server Using the Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Échec de la synchronisation du cube

QoEMetrics peut contenir des enregistrements non valides en fonction des horloges de l’utilisateur final. Si le décalage temporel est supérieur à 60 ans, l’importation du cube échouera.
  
 Cochez les cases min et Max StartTime/EndTime à l’aide des options ci-dessous. Recherchez et supprimez des enregistrements à l’avenir et à un futur éloigné, mais ils ne peuvent pas être pris en considération et ils vont rompre les processus de synchronisation.
  
- Sélectionnez MIN (StartTime) à partir de CqdPartitionedStreamView
    
- SELECT MAX (StartTime) à partir de CqdPartitionedStreamView
    
- Sélectionnez MIN (EndTime) à partir de CqdPartitionedStreamView
    
- Sélectionner MAX (EndTime) à partir de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tâches consécutives à l’installation

### <a name="importing-buildings-and-networks"></a>Importation de bâtiments et de réseaux

Après avoir installé CQD, effectuez les tâches de configuration suivantes :
  
1. Définir des types de construction (recommandé)
    
2. Définir les types de propriété de création (recommandé)
    
3. Définir des types de réseau (fortement recommandé)
    
4. Importer des bâtiments (recommandé)
    
5. Importer des sous-réseaux (recommandé)
    
### <a name="define-building-types"></a>Définir des types de construction

Les types de construction sont utilisés pour décrire les différentes définitions ou types de bâtiments au sein de votre organisation. 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
範例
  
- Siège social
    
- Bureau distant
    
- Emplacement de l’entreprise conjointe
    
  **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Les paramètres BuildingTypeId et BuildingTypeDesc sont obligatoires.
  
### <a name="define-building-ownership-types"></a>Définition des types de propriété de génération

Les types de propriété sont utilisés pour distinguer les biens loués vs.
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
範例
  
- Contoso avec bail non RE&amp;F
    
- Contoso bail RE&amp;F
    
- Contoso, propriétaire
    
- Filiale louée
    
  **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

Les paramètres OwnershipTypeId et OwnershipTypeDesc sont obligatoires. 
  
### <a name="define-network-names"></a>Définir les noms réseau

Les types de réseau sont utilisés pour décrire différents types de réseaux au sein de l’organisation. Cela vous permet de filtrer les types de réseau spécifiques (ou de les filtrer).
  
> [!NOTE]
> Il est vivement recommandé de définir des noms réseau, mais cela est facultatif. Si vous décidez de ne pas définir de noms réseau, vérifiez que chaque entrée CqdNetwork a un BuildingId de 0. 
  
範例
  
- VPN
    
- EXERCICES
    
  **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Les paramètres NetworkNameID et NetworkName sont obligatoires, mais le paramètre type est facultatif mais recommandé.
  
### <a name="import-buildings"></a>Importer des bâtiments

L’importation de bâtiments vous donne la possibilité de créer des informations spécifiques (appels médiocres par bâtiment sur WiFi/Wired, etc.). 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Avant d’importer un nouveau bâtiment, un BuildingKey prédéfini doit déjà être identifié. Pour ce faire, émettez la commande SQL « SELECT MAX (BuildingKey) FROM CqdBuilding » pour identifier la valeur actuelle et ajouter 1 au résultat.
  
 **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

Les paramètres BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId sont obligatoires, les autres paramètres sont facultatifs.
  
### <a name="import-subnets"></a>Importer des sous-réseaux

L’importation de bâtiments vous donne la possibilité de créer des informations spécifiques (appels médiocres par bâtiment sur WiFi/Wired, etc.). 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Importez des sous-réseaux et mappez-les aux bâtiments importés lors de la dernière étape. Si vous décidez de ne pas renseigner NetworkName, assurez-vous que chaque entrée de cette table utilise un NetworkNameID de 0.
  
 **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Le réseau et les paramètres UpdatedDate sont obligatoires, les autres paramètres sont facultatifs.
  
### <a name="optional-bssid"></a>Facultatif : BSSID

Le remplissage des informations BSSID vous donne une corrélation de flux WiFi supplémentaire par contrôleur ou radio. Cela s’ajoute au filtrage par construction ou sous-réseau. 
  
 **Exemple de syntaxe SQL**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**Détails de l’CqdBssidTable**

|**Comme illustré dans CQD**|**Table CQDBssid**|**Exemples d’entrées**|
|:-----|:-----|:-----|
|NName AP  <br/> |POINT  <br/> |API  <br/> |
|BBssid  <br/> |MODES  <br/> |00-00-00-00-00-00 (vous devez utiliser le fformat délimité)  <br/> |
|Contrôleur  <br/> |Construit  <br/> |AP d’Aruba 7  <br/> |
|Device  <br/> |capot  <br/> |Controller1  <br/> |
|Option  <br/> |PHY  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Traitement des données importées

Par défaut, une fois que vous avez importé des données de création/réseau, il s’applique uniquement aux enregistrements générés après cette date. 
  
Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devez exécuter la procédure stockée CqdUpdateBuilding, comme indiqué ci-dessous : 
  
Donnez-lui la date de votre premier enregistrement (identifiez-la à l’aide de la commande SELECT MIN (StartTime) FROM CqdPartitionedStreamView SQL), une date de demain, puis la valeur NULL pour les deux dernières valeurs.
  
Une fois que les données sont associées à des données de flux, le cube SSIS doit retraiter tous les enregistrements. Cela s’applique également lors de l’ajout en bloc de données BSSID/ISP. Assurez-vous que l’option « traiter tout le processus » est sélectionnée.
  

