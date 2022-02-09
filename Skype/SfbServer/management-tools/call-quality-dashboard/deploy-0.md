---
title: Déployer le Tableau de bord de qualité des appels pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : Découvrez le processus de déploiement du Tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: be6164c7b73a80c0557ea0814efddf59214a5481
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396346"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Déployer le Tableau de bord de qualité des appels pour Skype Entreprise Server
 
**Résumé :** Découvrez le processus de déploiement du Tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
## <a name="deployment-overview"></a>Présentation du déploiement

Le tableau de bord de qualité des appels (CQD) se compose de trois composants principaux :
  
- **Base de données** d’archivage, où les données de qualité de l’expérience (QoE) sont répliquées et stockées.
    
- **Cube**, où les données de la base de données d’archivage QoE sont agrégées pour un accès optimisé et rapide.
    
- **Portail**, où les utilisateurs peuvent facilement interroger et visualiser des données QoE.
    
![Composants CQD.](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Le processus de configuration de qoE Archive implique la création de la base de données d’archivage QoE, le déploiement d’une procédure stockée SQL Server qui déplace les données de la base de données de mesures QoE source vers la base de données d’archivage QoE et la configuration du travail de l’agent SQL Server pour exécuter la procédure stockée à intervalles réguliers. 
  
Le déploiement de cube obtient des informations de l’utilisateur sur l’emplacement de l’archive QoE, déploie le cube et définit un travail d’agent SQL Server normal qui actualisera le cube à intervalles réguliers.
  
L’installation du portail crée une base de données de référentiel qui stocke le mappage des utilisateurs CQD avec les rapports/requêtes de chaque utilisateur. Il définit ensuite une application web IIS qui est le tableau de bord dans lequel les utilisateurs peuvent voir un ensemble prédéfinis de rapports, ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données à partir du cube. L’installation du portail crée deux applications web supplémentaires qui exposent des API pour que les utilisateurs accèdent par programme au référentiel et au cube. (Ces API sont également utilisées en interne par le tableau de bord.)
  

|**Étape**|**Étapes**|**Rôles et appartenance à un groupe**|**Documentation**|
|:-----|:-----|:-----|:-----|
|Installez le matériel et les logiciels prérequis.  <br/> |Choisissez la configuration du CQD et choisissez un SQL Server à partir duquel effectuer l’installation.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Section « Conditions préalables à l’installation » dans la documentation de déploiement.  <br/> |
|Installez le CQD.  <br/> |Exécutez le MSI suivant le document de déploiement.  <br/> |Pour effectuer l’installation, le compte d’installation doit être un utilisateur de domaine membre du groupe Administrateurs local et ayant accès en lecture à la base de données de mesures QoE sur le serveur de surveillance.  <br/> |Sections « Comptes et étapes de déploiement » dans la documentation de déploiement.  <br/> |
|Accorder l’accès utilisateur.  <br/> |Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7.0. Pour plus d’informations, voir [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Gestion de l’accès des utilisateurs pour la section Portail de la documentation de déploiement.  <br/> |
|Facultatif : fournir des informations de mappage de sous-réseau.  <br/> |Remplir le réseau et créer des tables de mappage dans la base de données d’archivage QoE.  <br/> |Un compte avec un accès en écriture à la base de données d’archivage QoE.  <br/> |Section « Informations sur le sous-réseau » dans la documentation de l’utilisateur.  <br/> |
   


Le déploiement du tableau de bord de qualité des appels implique la configuration de l’infrastructure et l’installation du logiciel. La procédure suivante décrit le processus.
  
## <a name="deployment-steps"></a>Étapes de déploiement

1. Copiez le CallQualityDashboard.msi sur l’ordinateur sur lequel le composant de base de données d’archivage du CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server installé). 
    
2. Exécutez le MSI (Windows vous invitez à exécuter avec des privilèges d’administrateur, faites-le). 
    
3. Acceptez le CLA.
    
4. Sélectionnez le dossier de destination où se trouvent les fichiers liés aux composants du Tableau de bord de qualité des appels ou acceptez l’emplacement par défaut.
    
5. Sélectionnez toutes les fonctionnalités.
    
6. Dans la page Configuration de l’archive QoE, fournissez les informations suivantes :
    
   - **Les mesures QoE SQL Server :** SQL Server instance pour laquelle se trouve la base de données de mesures QoE (il s’agit de la source de données).
    
   - **Nom de l’SQL Server QoE** : il s’agit d’un champ en lecture seule et corrigé au nom de domaine complet de l’ordinateur local. La DB d’archivage ne peut être installée que sur l’ordinateur local.
    
   - **Instance d’archivage QoE SQL Server :** nom d’SQL Server d’archivage local pour l’endroit où la DB d’archivage doit être créée. Pour utiliser une instance SQL Server par défaut, laissez ce champ vide. Pour utiliser une instance SQL Server, spécifiez le nom de l’instance (par exemple, le nom après «\" »).
    
   - **Base de données d’archivage QoE :** Par défaut, cette option est définie sur « Créer une nouvelle base de données ». Étant donné que la mise à niveau de la base de données d’archivage n’est pas prise en charge, la seule circonstance dans laquelle l’option « Utiliser la base de données existante » peut être utilisée est si la base de données d’archivage existante possède le même schéma que le build à installer.
    
   - **Répertoire de fichiers de base de données :** Chemin d’accès à l’endroit où les fichiers de base de données (.mdf et .ldf) de la base de données d’archivage doivent être placés. Il doit être sur un lecteur (HDD2 dans la configuration matérielle recommandée) distinct du système d’exploitation. Étant donné que les noms de fichiers sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichier.
    
   - **Utilisez plusieurs partitions :** La valeur par défaut est « Partition multiple », ce qui nécessite une édition d’Enterprise ou une édition SQL Server. Pour l’édition Standard, sélectionnez l’option « Partition unique ». Notez que les performances de traitement du cube peuvent être touchées si une partition unique est utilisée.
    
     > [!NOTE]
     > La sélection de l’option Utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée. Pour la modifier, la fonctionnalité Cube doit d’abord être désinstallée, puis réinstallée à l’aide de l’option « Modifier » dans le Panneau de contrôle. 
  
   - **Répertoire de fichiers de partition :** Chemin d’accès à l’endroit où les partitions de la base de données d’archivage QoE doivent être placées. Il doit se faire sur un lecteur (HDD3 dans la configuration matérielle recommandée) distinct du lecteur de système d’exploitation et SQL de fichiers journaux de base de données. Étant donné que les noms de fichiers sont résolus dans l’installation, pour éviter tout conflit potentiel, il est recommandé d’utiliser un répertoire vide sans fichier.
    
   - Utilisateur du travail de **l’agent SQL - &amp;** Mot de passe du nom d’utilisateur : nom de compte de service de domaine et mot de passe (masqué) qui seront utilisés pour exécuter l’étape « Données d’archivage QoE » du travail de l’agent SQL Server (qui exécutera la procédure stockée pour extraire des données de la base de données de mesures QoE dans la base de données d’archivage, ce compte doit donc avoir un accès en lecture à la base de données de mesures QoE, comme indiqué dans la section Comptes). Ce compte doit également avoir une connexion dans l’instance d’archivage QoE SQL Server).
    
     > [!NOTE]
     > Le compte sous SQL Server instance est en cours d’exécution, tel que NT SERVICE\MSSQLSERVER, doit avoir accès/autorisation aux répertoires ci-dessus pour que l’installation réussisse. Pour plus d’informations, voir [Configure File System Permissions for Moteur de base de données Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. Lorsque vous cliquez ensuite, le programme d’installation effectue des vérifications préalables et signale si des problèmes sont rencontrés. Lorsque toutes les vérifications préalables sont requises, le programme d’installation passe à la page Configuration du cube. 
    
    > [!NOTE]
    > Si le programme d’installation affiche un message d’avertissement signalant que le service d’agent SQL Server pour l’instance QoE Archive SQL Server n’est pas en cours d’exécution, l’installation peut continuer, mais après l’installation, assurez-vous que le service agent SQL est en cours d’exécution et définissez le type de démarrage sur Automatique afin que le travail prévu s’exécute. 
  
8. Dans la page Configuration du cube, fournissez les informations suivantes :
    
   - **Nom de l’SQL Server QoE** : il s’agit d’un champ en lecture seule et corrigé au nom de domaine complet de l’ordinateur local. Le cube ne peut être installé qu’à partir de l’ordinateur qui dispose de la base de données d’archivage QoE (Remarque. Le cube lui-même peut être installé sur un ordinateur distant. Voir ci-dessous)
    
   - **Instance d’archivage QoE SQL Server :** SQL Server d’instance pour l’emplacement de la DB d’archivage QoE. Pour spécifier une instance SQL Server par défaut, laissez ce champ vide. Pour spécifier une instance SQL Server instance, entrez le nom de l’instance (par exemple, le nom après «\" »). Si le composant d’archivage QoE a été sélectionné pour l’installation, ce champ sera pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.
    
   - **Serveur d’analyse** de cube SQL Server nom de l’instance analysis service pour l’emplacement de création du cube. Il peut s’agit d’un autre ordinateur, mais l’utilisateur qui installe doit être membre des administrateurs de serveur de l’instance SQL Server Analysis Service.
    
     > [!NOTE]
     >  Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, voir [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **Utilisez plusieurs partitions :** La valeur par défaut est « Partition multiple », ce qui nécessite une édition d’Enterprise ou une édition SQL Server. Pour l’édition Standard, sélectionnez l’option « Partition unique ». Notez que les performances de traitement du cube peuvent être touchées si une partition unique est utilisée.
    
     > [!NOTE]
     >  La sélection de l’option Utiliser plusieurs partitions ne peut pas être modifiée une fois l’installation terminée. Pour la modifier, la fonctionnalité Cube doit d’abord être désinstallée, puis réinstallée à l’aide de l’option « Modifier » dans le Panneau de contrôle.
  
   - **Utilisateur du cube - Nom d’utilisateur &amp; Mot de passe** : nom de compte de service de domaine et mot de passe (masqué) qui déclenchent le traitement du cube. Si le composant d’archivage QoE a été sélectionné pour l’installation, ce champ sera pré-rempli avec la valeur fournie dans la page Configuration de l’archive pour l’utilisateur du travail de l’agent SQL, mais nous vous recommandons de spécifier un autre compte de service de domaine afin que le programme d’installation puisse lui accorder le privilège le moins requis.
    
9. Lorsque vous cliquez sur suivant, une autre série de validations est effectuée et tout problème est signalé. Une fois la validation terminée, le programme d’installation passe à la page Configuration du portail. 
    
10. Dans la page Configuration du portail, fournissez les informations suivantes :
    
    - **Archive QoE SQL Server :** SQL Server instance pour l’emplacement de la base de données d’archivage QoE. Notez que contrairement à la page Configuration de l’archive QoE et à la page Configuration du cube, le nom de l’ordinateur n’est pas fixe et doit être fourni. Si le composant d’archivage QoE a été sélectionné pour l’installation, ce champ sera pré-rempli avec la valeur fournie dans la page Configuration de l’archive QoE.
    
    - **Serveur d’analyse** de cube : SQL Server’instance analysis service pour l’emplacement du cube. Si le composant Cube a été sélectionné pour l’installation, ce champ sera pré-rempli avec la valeur fournie dans la page Configuration du cube.
    
    - **Référentiel SQL Server : SQL Server** instance où la base de données du référentiel doit être créée. Si le nom de l’instance de SQL Server où se trouve la base de données d’archivage QoE a été fourni plus tôt dans l’installation (dans d’autres composants), ce champ sera pré-rempli avec le nom d’instance de base de données d’archivage QoE SQL Server. Il peut s’SQL Server instance.
    
    - **Base de données de référentiel :** Par défaut, l’option est définie sur « Créer une nouvelle base de données ». Étant donné que la mise à niveau de la base de données du référentiel n’est pas prise en charge, la seule circonstance dans laquelle l’option « Utiliser la base de données existante » peut être utilisée est si la base de données de référentiel existante possède le même schéma que le build à installer.
    
    - **Utilisateur du pool d’applications IIS - Nom d’utilisateur &amp; Mot de passe :** compte sous le compte sur qui le pool d’applications IIS doit s’exécuter. Les champs Nom d’utilisateur et Mot de passe sont grisés si les comptes système intégrés sont sélectionnés. Ces champs ne seront activés que si « Autre » est sélectionné dans la zone de baisse afin que l’utilisateur puisse entrer les informations du compte de service de domaine.
    
11. Lorsque vous cliquez sur suivant, la dernière série de validations est effectuée pour vous assurer que les instances SQL Server sont accessibles à l’aide des informations d’identification fournies et qu’IIS est disponible sur l’ordinateur. Une fois la validation terminée, le programme d’installation procède à l’installation. 
    
Une fois le programme d’installation terminé, il est fort probable que le travail de l’agent SQL Server soit en cours, en faisant le chargement initial des données QoE et du traitement du cube. Selon la quantité de données dans QoE, le portail n’aura pas encore de données disponibles pour l’affichage. Pour vérifier l’état de la charge de données et du traitement du cube, allez sur  `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Notez que l’URL de vérification de l’état du traitement du cube de téléchargement est sensible à la cas. Si vous entrez « health » l’URL ne fonctionne pas. Vous devez entrer « Health » à la fin de l’URL avec un H majuscule. 
  
Les messages journaux détaillés s’afficheront si le mode débogage est activé. Pour activer le mode débogage, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La page du portail principal est accessible via  `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Gestion de l’accès des utilisateurs pour le portail

Pour gérer l’autorisation des utilisateurs sur le portail, nous vous recommandons d’utiliser l’autorisation d’URL, qui a été introduite dans IIS 7.0. Pour plus d’informations sur la sécurité IIS, voir [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Tout site web ou application web hérite de l’autorisation d’URL par défaut configurée pour l’ensemble des services Internet (IIS), qui est généralement « Autoriser tous les utilisateurs ». Si l’accès au portail doit être plus restrictif, les administrateurs peuvent accorder l’accès uniquement au groupe spécifique d’utilisateurs en éditant les « règles d’autorisation ».
  
![Déployer la qualité des appels : règles d’autorisation dans IIS.](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L’icône Règles d’autorisation ne doit pas être confondue avec « Autorisation .NET » sous la section ASP.NET, qui est un mécanisme d’autorisation différent. 
  
Les administrateurs doivent d’abord supprimer la règle héritée « Autoriser tous les utilisateurs ». Cela empêche les utilisateurs non autorisés d’accéder au portail.
  
![Déployez le CQD.](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Ensuite, les administrateurs doivent ajouter de nouvelles règles d’autorisation et accorder à des utilisateurs spécifiques l’autorisation d’accéder au portail. Il est recommandé de créer un groupe local appelé « CQDPortalUsers » pour gérer les utilisateurs.
  
![Déployer le tableau de bord de qualité des appels.](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Les détails de configuration sont stockés dans le web.config situé dans le répertoire physique du portail.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

L’étape suivante consiste à configurer le tableau de bord du tableau de bord du tableau de bord. Une fois que les utilisateurs sont authentifiés par IIS, ils doivent avoir des autorisations de fichier sur le répertoire CQD pour accéder au contenu du portail web. Il est possible de modifier les ACA via l’onglet de sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs individuels ou des groupes ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichier intactes. Modifiez plutôt le paramètre IIS pour utiliser le processus de travail IIS pour accéder au répertoire CQD, quel que soit l’utilisateur authentifié. 
  
> [!IMPORTANT]
> Il est important de modifier uniquement ce paramètre pour l’application CQD, et non pour les deux applications API : QoEDataService et QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuration de l’accès aux fichiers pour le tableau de bord

1. Ouvrez l’Éditeur de configuration pour le CQD.
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Sous Section, choisissez **system.webServer/serverRuntime**.
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.
    
     ![Déployer le tableau de bord de qualité des appels - Éditeur de configuration.](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Cliquez **sur** Appliquer sur le côté droit de la page.
    
## <a name="known-issues"></a>Problèmes connus

### <a name="the-cqd-shows-no-data-after-deployment"></a>Le CQD n’affiche aucune donnée après le déploiement

Vous pouvez recevoir l’erreur suivante :

*Nous n’avons pas pu exécuter la requête lors de son exécution sur le cube. Utilisez l’Éditeur de requêtes pour modifier la requête et résoudre les problèmes. Assurez-vous également que le cube est accessible.*

Cela signifie que le cube doit être traitée dans SQL Server Analysis Services avant d’être utilisé dans le CQD. Vous pouvez résoudre ce problème en suivant les étapes suivantes :

1. Ouvrez SQL Management Studio et sélectionnez **Analysis Services**.

2. Développez **l’objet QoECube** , sélectionnez **Mesure QoE**, cliquez avec le bouton droit, puis choisissez **Parcourir**. 

    Si cela renvoie un navigateur vide, le cube n’a pas encore été utilisé.

3. Cliquez avec le bouton **droit sur QoE Metric** angain et choisissez **Processus**.

4. Lorsque le traitement est terminé, cliquez à nouveau avec le bouton droit sur l’objet, puis choisissez **Parcourir** pour confirmer que la page du navigateur affiche désormais les données. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Les utilisateurs ont des difficultés à se connecter car le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS

Dans de rares cas, le programme d’installation ne parvient pas à créer les paramètres corrects dans IIS. Une modification manuelle est nécessaire pour permettre aux utilisateurs de se connecter au CQD. Si les utilisateurs ont des difficultés à se connecter, suivez les étapes suivantes :
  
1. Ouvrez le Gestionnaire des services Internet et accédez au site Web par défaut.
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Cliquez sur « Authentification ». Si les paramètres « Authentification anonyme », « emprunt d’identité ASP.NET », « Authentification de formulaire » et « Authentification Windows » ne correspondent pas aux paramètres indiqués ci-dessous, modifiez-les manuellement pour qu’ils correspondent aux paramètres ci-dessous. Tous les autres mécanismes d’authentification doivent être désactivés.
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Pour « Authentification Windows », cliquez sur Advanced Paramètres sur le côté droit.
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Définissez « Protection étendue » pour accepter et cochez la case « Activer l’authentification en mode noyau ».
    
     ![Déployer le tableau de bord de qualité des appels.](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Répétez les étapes ci-dessus pour chacune des entrées « CQD », « QoEDataService » et « QoERepositoryService » sous « Site Web par défaut ».
    
Pour les liaisons de port HTTP et HTTPS, le programme d’installation crée des liaisons de port sur les numéros de port par défaut (port 80 pour HTTP et port 443 pour HTTPS). S’il existe un autre site web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et le comportement IIS ne peut pas être prévisible. La meilleure façon d’éviter ce problème est de vous assurer qu’aucun autre site web n’est mappé aux ports 80 et 443 avant d’installer le CQD. 
  
Pour activer SSL/TLS dans IIS et forcer les utilisateurs à se connecter via httpS sécurisé au lieu de HTTP :
  
1. Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)). Une fois terminé, remplacez  `http` par `https`.
    
2. Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir Comment activer le chiffrement SSL pour une instance de SQL Server à l’aide de [Microsoft Management Console](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Échec de la synchronisation du cube

QoEMetrics peut contenir des enregistrements non valides basés sur les horloges de l’utilisateur final. Si la inclinaison de temps est supérieure à 60 ans, l’importation du cube échoue.
  
 Vérifiez les heures de début/fin min et max à l’aide des sélections ci-dessous. Recherchez et supprimez des enregistrements dans le passé et dans un futur très distant, ils peuvent être ignorés et ils décomposeront les processus de synchronisation.
  
- Select MIN(StartTime) FROM CqdPartitionedStreamView
    
- Select MAX(StartTime) FROM CqdPartitionedStreamView
    
- Select MIN(EndTime) FROM CqdPartitionedStreamView
    
- Select MAX(EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tâches post-installation

### <a name="importing-buildings-and-networks"></a>Importation de bâtiments et de réseaux

Après avoir installé le CQD, effectuez les tâches de configuration suivantes :
  
1. Définir les types de construction (recommandé)
    
2. Définir les types de propriété de construction (recommandé)
    
3. Définir les types de réseau (vivement recommandé)
    
4. Importer des bâtiments (recommandé)
    
5. Importer des sous-réseaux (recommandé)
    
### <a name="define-building-types"></a>Définir les types de construction

Les types de bâtiment sont utilisés pour décrire les différentes définitions ou types de bâtiments au sein de votre organisation. 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Exemples
  
- Headquarters
    
- Remote Office
    
- Emplacement de joint-lieu
    
  **Exemple SQL syntaxe**
  
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
  
### <a name="define-building-ownership-types"></a>Définir les types de propriété de construction

Les types de propriété sont utilisés pour distinguer les biens propriétaires et les biens en bail.
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Exemples
  
- Contoso leased non-REF&amp;
    
- Contoso Leased REF&amp;
    
- Contoso Owned
    
- Filiale en bail
    
  **Exemple SQL syntaxe**
  
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
  
### <a name="define-network-names"></a>Définir des noms de réseau

Les types de réseau sont utilisés pour décrire différents types de réseaux au sein de l’organisation. Cela vous permet de filtrer des types réseau spécifiques (ou de les filtrer).
  
> [!NOTE]
> Il est vivement recommandé de définir des noms de réseau, mais il est facultatif. Si vous décidez de ne pas définir de noms réseau, assurez-vous que chaque entrée CqdNetwork a un BuildingId de 0. 
  
Exemples
  
- VPN
    
- LABO
    
  **Exemple SQL syntaxe**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Les paramètres NetworkNameID et NetworkName sont obligatoires, le paramètre NetworkType est facultatif mais recommandé.
  
### <a name="import-buildings"></a>Importer des bâtiments

L’importation de bâtiments vous permet d’obtenir des informations spécifiques (appels médiocres par bâtiment sur WiFi/Fil, etc.). 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Avant d’importer un nouveau bâtiment, une clé BuildingKey prédéfinë doit déjà être identifiée. Pour ce faire, émettre la commande « SELECT MAX(BuildingKey) FROM CqdBuilding » SQL pour identifier la valeur actuelle et ajouter 1 au résultat.
  
 **Exemple SQL syntaxe**
  
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

L’importation de bâtiments vous permet d’obtenir des informations spécifiques (appels médiocres par bâtiment sur WiFi/Fil, etc.). 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée.
  
Importez les sous-réseaux et mapillez-les aux bâtiments importés à la dernière étape. Si vous décidez de ne pas remplir NetworkName, assurez-vous que chaque entrée de ce tableau utilise un NetworkNameID de 0. Pour plus d’informations sur SQL syntaxe et les paramètres du tableau de bord de qualité des appels, voir Utiliser le tableau de bord de qualité des appels [pour Skype Entreprise Server](./use.md).
  
 **Exemple SQL syntaxe**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

Les paramètres Network et UpdatedDate sont obligatoires, les autres paramètres sont facultatifs.
  
### <a name="optional-bssid"></a>Facultatif : BSSID

Le fait de remplir les informations BSSID vous donne une corrélation de flux WiFi supplémentaire par contrôleur ou radio. Cela s’ajoute au filtrage par bâtiment ou sous-réseau. 
  
 **Exemple SQL syntaxe**
  
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

**Détails de CqdBssidTable**

|**Comme indiqué dans le CQD**|**CQDBssid Table**|**Exemples d’entrées**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (vous devez utiliser la forme délimitée)  <br/> |
|Contrôleur  <br/> |Création  <br/> |Aruba AP 7  <br/> |
|Appareil  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Traitement des données importées

Par défaut, une fois que vous importez des données de construction/réseau, elle s’applique uniquement aux enregistrements générés après ce moment. 
  
Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devez exécuter la procédure stockée CqdUpdateBuilding, comme illustré ci-dessous : 
  
Donnez-lui la date de votre premier enregistrement (identifiez qu’à l’aide de la commande Select MIN(StartTime) FROM CqdPartitionedStreamView SQL ), un EndDate de demain, puis NULL pour les deux dernières valeurs.
  
Une fois que les données sont associées aux données de flux, le cube SSIS doit retraiter tous les enregistrements. Cela s’applique également lors de l’ajout en bloc de données BSSID/ISP. Assurez-vous que « Processus complet » est sélectionné.
