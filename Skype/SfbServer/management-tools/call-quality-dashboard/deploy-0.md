---
title: Déployer le tableau de bord appel qualité pour Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Résumé : Découvrez le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 31e1dc8d5508c7d3d31de0ec3af0b9c8c06a6c40
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372640"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Déployer le tableau de bord appel qualité pour Skype pour Business Server 2015
 
**Résumé :** Découvrez le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
## <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Tableau de bord de qualité d’appel (CQD) se compose de trois composants principaux :
  
- **Base de données d’archivage**, où les données de qualité de l’expérience (QoE) sont répliquées et stockées.
    
- **Cube**, où les données à partir de la base de données QoE Archive sont regroupées pour optimisé et un accès rapide.
    
- **Portail**, où les utilisateurs peuvent facilement des requêtes et visualiser les données QoE.
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Le processus d’installation pour l’archivage QoE implique la création de la base de données QoE Archive, le déploiement d’une procédure stockée SQL Server qui déplace les données de la source de base de données des mesures QoE dans la base de données QoE Archive et configurer le travail de l’Agent SQL Server pour exécuter stockées procédure à intervalles réguliers. 
  
Déploiement de cube Obtient des informations à partir de l’utilisateur où le QoE Archive se trouve, déploie le cube et configure un travail de l’agent SQL Server régulière qui sera actualiser le cube à intervalle régulier.
  
Installation de portail crée une base de données de référentiel qui stocke le mappage d’utilisateurs CQD à rapports/requêtes chaque utilisateur. Il configure ensuite une application web IIS est le tableau de bord dans lequel les utilisateurs peuvent voir un ensemble prédéfini de rapports ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données du cube. L’installation du portail crée deux applications web supplémentaires qui expose l’API pour les utilisateurs à accéder par programme le référentiel et le cube. (Ces API sont utilisées en interne par le tableau de bord.)
  

|**Phase**|**Étapes**|**Rôles et appartenances aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|Installer les logiciels et le matériel requis.  <br/> |Déterminer la configuration CQD, puis choisissez un serveur SQL Server à partir de laquelle effectuer l’installation.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Section « Conditions requises pour installer préalable » dans la documentation de déploiement.  <br/> |
|Installez CQD.  <br/> |Exécutez le fichier MSI suivant le document de déploiement.  <br/> |Pour exécuter le programme d’installation, le compte d’installation doit être un utilisateur de domaine qui est membre du groupe Administrateurs local et ont accès en lecture à la base de données des mesures QoE sur le serveur de surveillance.  <br/> |Sections « Comptes et étapes de déploiement » dans la documentation de déploiement.  <br/> |
|Accorder l’accès des utilisateurs.  <br/> |Pour gérer l’autorisation utilisateur sur le portail, nous recommandons l’utilisation de l’autorisation d’URL, ce qui a été introduite dans IIS 7.0. Pour plus d’informations, voir [Understanding IIS 7.0 l’autorisation d’URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Gestion de l’accès utilisateur pour la section du portail dans la documentation de déploiement.  <br/> |
|Facultatif : Fournir des informations de mappage de sous-réseau.  <br/> |Remplir le réseau et les tables de mappage de construction de base de données QoE Archive.  <br/> |Un compte avec accès en écriture à la base de données QoE Archive.  <br/> |Section « Fournir des informations de sous-réseau » dans la documentation de l’utilisateur.  <br/> |
   


Déploiement du tableau de bord qualité des appels implique la configuration de l’infrastructure et de l’installation du logiciel. La procédure suivante décrit le processus.
  
## <a name="deployment-steps"></a>Étapes du déploiement

1. Copier le CallQualityDashboard.msi sur l’ordinateur où le composant de base de données d’archivage de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server est installé). 
    
2. Exécutez le MSI (Windows vous invite à exécuter avec des privilèges d’administrateur, faites-le). 
    
3. Acceptez le CLUF.
    
4. Sélectionnez le dossier de destination où les fichiers liés aux composants du tableau de bord qualité d’appel seront est introuvable ou acceptez l’emplacement par défaut.
    
5. Sélectionnez toutes les fonctionnalités.
    
6. Dans la page Configuration de l’Archive QoE, fournissez les informations suivantes :
    
   - **Mesures QoE SQL Server :** Nom de l’instance SQL Server pour où se trouve la base de données des mesures QoE (il s’agit de la source de données).
    
   - **Nom du serveur SQL QoE Archive :** Ce champ en lecture seule et fixe sur le nom de domaine complet de l’ordinateur local. Base de données d’archivage peut être installé uniquement sur l’ordinateur local.
    
   - **QoE Archive une Instance SQL Server :** Un nom d’instance SQL Server local pour lequel la base de données d’archivage doit être créé. Pour utiliser une instance de SQL Server par défaut, laissez ce champ vide. Pour utiliser une instance nommée de SQL Server, spécifiez le nom d’instance (par exemple, le nom après le «\").
    
   - **Base de données QoE Archive :** Par défaut, cette option est définie sur « Créer nouvelle base de données ». Étant donné que la mise à niveau de la base de données Archive n’est pas pris en charge, le seul cas sous lequel l’option « Utiliser la base de données existante » peut être utilisée est si cette base de données existante a le même schéma que la version à installer.
    
   - **Répertoire du fichier de base de données :** Chemin d’accès où les fichiers de base de données (fichiers .mdf et .ldf) pour la base de données d’archivage doivent être placés. Il doit s’agir sur un lecteur distinct (HDD2 dans la configuration matérielle recommandée) du système d’exploitation. Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide avec aucun fichier n’est utilisé.
    
   - **Utilisez plusieurs Partitions :** La valeur par défaut est défini sur « Plusieurs partition », ce qui nécessite l’édition Business Intelligence ou Enterprise edition de SQL Server. Pour Standard edition, sélectionnez l’option « Partition unique ». Notez que les performances de traitement du cube peuvent être affectés si seule Partition est utilisée.
    
     > [!NOTE]
     > La sélection pour l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée. Pour modifier, le Cube doit être la première fonctionnalité désinstallé et réinstallé utilisant l’option « Modifier » dans le panneau de configuration. 
  
   - **Répertoire du fichier de partition :** Chemin d’accès où les partitions pour cette base de données QoE doivent être placées. Il doit s’agir sur un lecteur distinct (HDD3 dans la configuration matérielle recommandée) du lecteur de système d’exploitation et d’un lecteur de fichiers du journal de base de données SQL. Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide avec aucun fichier n’est utilisé.
    
   - **Utilisateur de travail de l’Agent SQL - nom d’utilisateur &amp; le mot de passe :** Nom de compte de service de domaine et le mot de passe (masqué) qui sera utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent SQL Server (qui s’exécute la procédure stockée pour extraire les données de base de données de mesures QoE dans base de données Archive, ce compte doit avoir accès en lecture à la base de données QoE mesures,  comme indiqué dans la section comptes. Ce compte doit également disposer d’une connexion dans l’Instance de SQL Server Archive QoE).
    
     > [!NOTE]
     > L’instance SQL Server s’exécutant sous, telles que NT SERVICE\MSSQLSERVER, le compte doit avoir accès aux répertoires donné ci-dessus pour réussir l’installation. Pour plus d’informations, voir [Configurer des autorisations de système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Lorsque vous cliquez sur Suivant, le programme d’installation effectue les vérifications préalables et rapport si des problèmes sont rencontrés. Lorsque les vérifications préalables toutes les pass, le programme d’installation est dirigés vers la page Configuration du Cube. 
    
    > [!NOTE]
    > Si le programme d’installation affiche un avertissement indiquant que le service SQL Server Agent pour l’instance SQL Server de QoE Archive ne fonctionne pas actuellement, procéder à l’installation, mais après l’installation, assurez-vous que l’Agent SQL est en cours d’exécution et le type de démarrage de service Automatique afin que la tâche planifiée s’exécute. 
  
8. Dans la page Configuration du Cube, fournissez les informations suivantes :
    
   - **Nom du serveur SQL QoE Archive :** Ce champ en lecture seule et fixe sur le nom de domaine complet de l’ordinateur local. Cube peut être installé uniquement à partir de l’ordinateur qui contient la base de données QoE Archive (Note. Cube lui-même peut être installé sur un ordinateur distant. Voir ci-dessous)
    
   - **QoE Archive une Instance SQL Server :** Nom d’instance de SQL Server pour où se trouve la base de données Archive QoE. Pour spécifier une instance de SQL Server par défaut, laissez ce champ vide. Pour spécifier une instance nommée de SQL Server, entrez le nom d’instance (par exemple, le nom après le «\"). Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’Archive QoE.
    
   - **Cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour lequel le cube doit être créé. Il peut s’agir d’un autre ordinateur, mais l’utilisateur de l’installation doit être un membre du groupe Administrateurs de serveur de l’instance de SQL Server Analysis Services cible.
    
     > [!NOTE]
     >  Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, voir [Accorder des autorisations administrateur du serveur (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Utilisez plusieurs Partitions :** La valeur par défaut est défini sur « Plusieurs partition », ce qui nécessite l’édition Business Intelligence ou Enterprise edition de SQL Server. Pour Standard edition, sélectionnez l’option « Partition unique ». Notez que les performances de traitement du cube peuvent être affectés si seule Partition est utilisée.
    
     > [!NOTE]
     >  La sélection pour l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée. Pour modifier, le Cube doit être la première fonctionnalité désinstallé et réinstallé utilisant l’option « Modifier » dans le panneau de configuration.
  
   - **Utilisateur - nom d’utilisateur de cube &amp; le mot de passe :** Nom de compte de service de domaine et le mot de passe (masqué) qui déclenche le traitement du cube. Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’archivage pour l’utilisateur de travail de l’Agent SQL, mais nous vous recommandons de spécifier un compte de service de domaine différent afin que le programme d’installation peut accorder le Privilège requis à celui-ci.
    
9. Lorsque vous cliquez sur Suivant, une autre série de validation est effectuée et tout problème est reportée. En cas de réussite de la validation, le programme d’installation est dirigés vers la page Configuration du portail. 
    
10. Dans la page Configuration du portail, fournissez les informations suivantes :
    
    - **QoE Archive SQL Server :** Nom d’instance de SQL Server pour où se trouve la base de données QoE Archive. Notez que, contrairement à la page Configuration de l’Archive QoE et la page Configuration du Cube, le nom de l’ordinateur n’est pas résolu et doit être fourni. Si le composant QoE Archive a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration de l’Archive QoE.
    
    - **Cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour où se trouve le cube. Si le composant de Cube a été sélectionné pour l’installation, ce champ est prérempli avec la valeur fournie dans la page Configuration du Cube.
    
    - **Référentiel SQL Server :** Nom d’instance SQL Server où la base de données de référentiel doit être créé. Si le nom d’instance SQL Server pour où se trouve la base de données QoE Archive a été fourni plus haut dans l’installation (dans d’autres composants), ce champ est prérempli avec le nom d’instance de base de données SQL Server QoE Archive. Il peut s’agir d’une instance de SQL Server.
    
    - **Base de données de référentiel :** Par défaut, l’option est définie sur « Créer nouvelle base de données ». Étant donné que la mise à niveau de la base de données de référentiel n’est pas pris en charge, le seul cas sous lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données de référentiel existant a le même schéma que la version à installer.
    
    - **Utilisateur du Pool d’applications IIS - nom d’utilisateur &amp; le mot de passe :** Le compte du pool d’applications IIS doit s’exécuter sous. Les champs nom d’utilisateur et mot de passe seront grisés si les comptes intégrés sont sélectionnés. Ces champs seulement seront activés si « Other » est sélectionnée dans la liste déroulante afin que l’utilisateur puisse entrer les informations de compte de service de domaine.
    
11. Lorsque vous cliquez sur Suivant, la dernière série de validation sera effectuée pour s’assurer que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et que IIS est disponible sur l’ordinateur. En cas de réussite de la validation, le programme d’installation poursuit l’installation. 
    
Lorsque le programme d’installation est terminé, probablement le travail de l’Agent SQL Server sera en cours, en effectuant le chargement initial des données QoE et le traitement du cube. Selon la quantité de données dans les données QoE, le portail n’aura données disponibles pour l’affichage encore. Pour vérifier l’état de la charge de données et le traitement du cube, accédez à `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Notez que l’URL de vérification de l’état du téléchargement de traitement de cube respecte la casse. Si vous entrez « santé », que l’URL ne fonctionneront pas. Vous devez entrer « Santé » à la fin de l’URL en majuscule H. 
  
Messages du journal détaillé seront affichera si le mode débogage est activé. Pour activer le mode de débogage, accédez à **%SYSTEMDRIVE%\Program Files\Skype pour Business 2015 CQD\QoEDataService\web.config**et mettre à jour de la ligne suivante afin que la valeur est définie sur **True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La principale page du portail est accessible via `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Gestion de l’accès des utilisateurs pour le portail

Pour gérer l’autorisation utilisateur sur le portail, nous recommandons l’utilisation de l’autorisation d’URL, ce qui a été introduite dans IIS 7.0. Pour plus d’informations sur la sécurité IIS, voir [Understanding IIS 7.0 l’autorisation d’URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
N’importe quelle application web de site ou héritent de la valeur par défaut de l’autorisation d’URL configuré pour l’ensemble IIS, qui est généralement « Autoriser tous les utilisateurs ». Si l’accès au portail doit être plus restrictif, puis administrateurs peuvent accorder un accès pour seulement le groupe d’utilisateurs spécifique en modifiant les « règles d’autorisation ».
  
![Déployer la qualité des appels - règles d’autorisation dans IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L’icône de règles d’autorisation ne doit ne pas être confondu avec l’autorisation « .NET » dans la section ASP.NET, qui est un mécanisme d’autorisation différentes. 
  
Les administrateurs doivent d’abord supprimer la règle héritée « autoriser tous les utilisateurs ». Cela empêche des utilisateurs non autorisés de l’accès au portail.
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Ensuite, les administrateurs doivent ajouter de nouvelles règles Autoriser et autoriser des utilisateurs spécifiques pour accéder au portail. Il est recommandé qu’un groupe local nommé « CQDPortalUsers » être créées pour gérer les utilisateurs.
  
![Déployer le Tableau de bord de la qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Les détails de configuration sont stockés dans le fichier web.config situé dans le répertoire physique du portail.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

L’étape suivante consiste à configurer le tableau de bord de la CQD. Une fois que les utilisateurs sont authentifiés par IIS, ils doivent disposer d’autorisations sur le répertoire CQD afin d’accéder au contenu de portail web. Il est possible de modifier les listes ACL par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs individuels ou des groupes ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichiers inchangés. Au lieu de cela, modifiez le paramètre IIS à utiliser le processus de travail IIS pour accéder au répertoire CQD quelle que soit l’utilisateur est authentifié. 
  
> [!IMPORTANT]
> Il est important de ne modifier ce paramètre pour l’application CQD et non pour les deux applications API : QoEDataService et QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuration de l’accès de fichier pour le CQD (tableau de bord)

1. Ouvrez l’éditeur de Configuration pour CQD.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Sous la Section, choisissez **system.webServer/serverRuntime**.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Remplacez authenticatedUserOverride **UseWorkerProcessUser**.
    
     ![Déployer le Tableau de bord de la qualité des appels - Éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Cliquez sur **Appliquer** dans la partie droite de la page.
    
## <a name="known-issues"></a>Problèmes connus

Dans les cas rares, le programme d’installation ne peut pas créer les paramètres appropriés dans IIS. Modification manuelle est nécessaire pour permettre aux utilisateurs de se connecter à la CQD. Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :
  
1. Ouvrir le Gestionnaire des services Internet haut, puis accédez au Site Web par défaut.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Cliquez sur « Authentification ». Si les « Authentification anonyme », « Emprunt d’identité ASP.NET », « Authentification par formulaire » et « Authentification Windows » ne correspondent pas les paramètres indiqués ci-dessous, manuellement les modifier pour faire correspondre les paramètres ci-dessous. Tous les autres mécanismes d’authentification doivent être désactivés.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Pour « Authentification Windows », cliquez sur Paramètres avancés sur le côté droit.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Accepter la valeur « Protection étendue » et la case à cocher « authentification en mode noyau activer ».
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Répétez les étapes ci-dessus pour chacune des entrées « CQD », « QoEDataService » et « QoERepositoryService » sous « Site Web par défaut ».
    
Pour les liaisons de port HTTP et HTTPS le programme d’installation crée les liaisons de port sur les numéros de port par défaut (port 80 pour HTTP) et le port 443 pour le protocole HTTPS. S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et le comportement IIS ne peut pas être prévu. La meilleure façon pour éviter ce problème est pour vous assurer qu’aucuns les autres sites Web n’est mappées sur les ports 80 et 443 avant d’installer CQD. 
  
Pour activer SSL/TLS dans IIS et forcer les utilisateurs à se connecter via le protocole HTTPS au lieu de HTTP secure :
  
1. Configurer le protocole SSL (Secure Sockets Layer) dans IIS, voir [Configuration de SSL dans IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Une fois que vous avez terminé, remplacez `http` avec `https`.
    
2. Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir [comment activer le chiffrement SSL pour une instance de SQL Server à l’aide de Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Échec de synchronisation de cube

QoEMetrics peut contenir des enregistrements non valides en fonction de l’utilisateur final horloges. Si le délai maximal autorisé est supérieure à 60 ans, l’importation de cube échoue.
  
 Vérifiez les Min et Max début/fin à l’aide des sélections ci-dessous. Rechercher et supprimer des enregistrements dans le futur dépassée et très éloigné, ils peuvent ne pas être et qu’ils seront décomposer les processus de synchronisation.
  
- Sélectionnez MIN(StartTime) de CqdPartitionedStreamView
    
- Sélectionnez MAX(StartTime) de CqdPartitionedStreamView
    
- Sélectionnez MIN(EndTime) de CqdPartitionedStreamView
    
- Sélectionnez MAX(EndTime) de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tâches de post-installation

### <a name="importing-buildings-and-networks"></a>Importation de bâtiments et les réseaux

Après l’installation de CQD, effectuez les tâches de configuration suivantes :
  
1. Définir des types de construction (recommandés)
    
2. Définir les types de propriété construction (recommandés)
    
3. Définir les types de réseau (recommandés)
    
4. Importation de bâtiments (recommandé)
    
5. Importation des sous-réseaux (recommandés)
    
### <a name="define-building-types"></a>Définir des Types de construction

Types de construction sont utilisés pour décrire les définitions de bâtiments différents types au sein de votre organisation. 
  
> [!NOTE]
> Cette étape est facultative mais recommandée. 
  
Exemples
  
- Siège social
    
- Bureau à distance
    
- Emplacement de l’entreprise commune
    
  **Exemple de syntaxe SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Les paramètres BuildingTypeId et BuildingTypeDesc sont requis.
  
### <a name="define-building-ownership-types"></a>Définir les Types de propriété de construction

Types de propriété sont utilisés pour distinguer les biens spécialisées vs détenus.
  
> [!NOTE]
> Cette étape est facultative mais recommandée. 
  
Exemples
  
- Contoso allouée non-RE&amp;F
    
- Connexion en bail Contoso RE&amp;F
    
- Propriété de Contoso
    
- Filiale spécialisée
    
  **Exemple de syntaxe SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

Les paramètres OwnershipTypeId et OwnershipTypeDesc sont requis. 
  
### <a name="define-network-names"></a>Définir les noms de réseau

Types de réseau sont utilisés pour décrire différents types de réseaux au sein de l’organisation. Cela vous donne la possibilité de filtrer (ou filtrer) les Types de réseau spécifiques.
  
> [!NOTE]
> Il est vivement recommandé de définir les noms de réseau, mais il est facultatif. Si vous décidez de ne définit ne pas les noms de réseau, vérifiez que le chaque entrée CqdNetwork a un BuildingId de 0. 
  
Exemples
  
- VPN
    
- ATELIER
    
  **Exemple de syntaxe SQL**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Les paramètres NetworkNameID et NetworkName sont nécessaires, le paramètre NetworkType est facultatif mais recommandé.
  
### <a name="import-buildings"></a>Importation de bâtiments

Importation de bâtiments vous donne la possibilité d’obtenir création insights spécifiques (appels médiocres par création/câblé Wi-Fi, etc.).. 
  
> [!NOTE]
> Cette étape est facultative mais recommandée. 
  
Avant d’importer une nouvelle génération vous disposez déjà d’un BuildingKey prédéfini identifié. Pour cela, exécutez la commande SQL « Sélectionnez MAX(BuildingKey) de CqdBuilding » pour identifier la valeur actuelle et ajouter des 1 sur le résultat.
  
 **Exemple de syntaxe SQL**
  
```
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

Le BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId paramètres sont obligatoires, les autres paramètres sont facultatifs.
  
### <a name="import-subnets"></a>Importer des sous-réseaux

Importation de bâtiments vous donne la possibilité d’obtenir création insights spécifiques (appels médiocres par création/câblé Wi-Fi, etc.).. 
  
> [!NOTE]
> Cette étape est facultative mais recommandée. 
  
Importer des sous-réseaux et les mapper aux bâtiments importés à l’étape précédente. Si vous décidez de ne pas remplir NetworkName, veillez à que chaque entrée de ce tableau utilise un NetworkNameID de 0.
  
 **Exemple de syntaxe SQL**
  
```
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

Informations BSSID vous permet de corrélation de flux Wi-Fi supplémentaire par contrôleur ou radio. Il s’agit en plus de filtrage de création ou le sous-réseau. 
  
 **Exemple de syntaxe SQL**
  
```
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

**Détails CqdBssidTable**

|**Comme indiqué dans CQD**|**Tableau CQDBssid**|**Entrées de l’exemple**|
|:-----|:-----|:-----|
|Name AP  <br/> |POINT D’ACCÈS  <br/> |POINT D’ACCÈS 1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (vous devez utiliser le format délimité)  <br/> |
|Contrôleur  <br/> |Bâtiment  <br/> |Aruba AP 7  <br/> |
|APPAREIL  <br/> |ess  <br/> |: Contrôleur1  <br/> |
|Case d’option  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Traitement des données importées

Par défaut, une fois que vous importez des données de création/réseau il s’applique uniquement aux enregistrements générés une fois que le point dans le temps. 
  
Pour ajouter une balise à tous les enregistrements précédents avec ces nouvelles données, vous devrez exécuter la procédure stockée de CqdUpdateBuilding comme indiqué ci-dessous : 
  
Lui donner la date de votre premier enregistrement (identifier à l’aide de la commande SQL sélectionnez de MIN(StartTime) de CqdPartitionedStreamView), une date de fin de demain, puis NULL pour les deux dernières valeurs.
  
Une fois les données sont associées à des données de flux de données, le Cube SSIS doit traiter à nouveau tous les enregistrements. Cela s’applique également lorsque en bloc de l’ajout de données BSSID/fournisseur de services Internet. Vérifiez que « Processus Full » est sélectionnée.
  

