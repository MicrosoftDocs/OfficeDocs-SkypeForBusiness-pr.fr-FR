---
title: Déployer le tableau de bord qualité appel pour Skype pour Business Server 2015
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
description: 'Résumé : En savoir plus sur le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: ff8f9bae2c292720bb3fd9943bc541a8eeb6759c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Déployer le tableau de bord qualité appel pour Skype pour Business Server 2015
 
**Résumé :** Obtenir des informations sur le processus de déploiement pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
## <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Appel de qualité du tableau de bord (CQD) se compose de trois composants principaux :
  
- **Archivage de base de données**, où les données de la qualité d’expérience (QoE) sont répliquées et stockées.
    
- **Cube**, où les données à partir de la base de données Archive de QoE sont regroupées pour optimisé et un accès rapide.
    
- **Portail**, où les utilisateurs peuvent facilement rechercher et visualiser les données QoE.
    
![Composants CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
Le processus d’installation pour l’archivage de QoE implique la création de la base de données Archive de QoE, le déploiement d’une procédure SQL Server stockées qui déplace les données de la source de base de données QoE métrique dans la base de données Archive de QoE et configuration de la tâche de l’Agent de SQL Server pour exécuter la commande stockées procédure à intervalles réguliers. 
  
Déploiement de cube Obtient des informations à l’utilisateur où le QoE Archive se trouve, déploie le cube et configure un travail d’agent SQL Server régulière qui actualise le cube à intervalle régulier.
  
Installation de portail crée une base de données de référentiel qui stocke le mappage des utilisateurs CQD aux rapports/requêtes chaque utilisateur. Il définit ensuite une application web IIS est le tableau de bord où les utilisateurs peuvent voir un ensemble de rapports prédéfinis ainsi que personnaliser et créer leurs propres requêtes pour visualiser les données du cube. L’installation du portail crée deux applications web supplémentaires qui expose des API permettant aux utilisateurs d’accéder par programme le référentiel et le cube. (Ces API sont utilisées en interne par le tableau de bord.)
  

|**Phase de**|**Étapes**|**Rôles et appartenance à un groupe**|**Documentation**|
|:-----|:-----|:-----|:-----|
|Installer les logiciels et le matériel requis.  <br/> |Choisissez la configuration CQD et choisissez un SQL Server à partir de laquelle effectuer l’installation.  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Section de « Installation configuration requise » dans la documentation de déploiement.  <br/> |
|Installation de CQD.  <br/> |Exécutez le fichier MSI suivant le document de déploiement.  <br/> |Pour exécuter le programme d’installation, le compte d’installation doit être un utilisateur de domaine qui est membre du groupe Administrateurs local et ont un accès en lecture à la base de données QoE métrique sur le serveur d’analyse.  <br/> |Sections « Comptes et étapes de déploiement » dans la documentation de déploiement.  <br/> |
|Accorder l’accès de l’utilisateur.  <br/> |Gérez les autorisations utilisateur sur le portail, nous recommandons à l’aide de l’autorisation d’URL, ce qui a été introduit dans IIS 7.0. Pour plus d’informations, consultez [Autorisation d’URL de présentation IIS 7.0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Utilisateur du domaine membre du groupe Administrateurs local.  <br/> |Gestion de l’accès utilisateur pour la section du portail dans la documentation de déploiement.  <br/> |
|Facultatif : Fournissent des informations de mappage de sous-réseau.  <br/> |Remplir le réseau et le mappage de création des tables dans la base de données Archive de QoE.  <br/> |Un compte avec un accès en écriture à la base de données Archive de QoE.  <br/> |Section « En fournissant les informations de sous-réseau » dans la documentation de l’utilisateur.  <br/> |
   
## 

Déploiement du tableau de bord qualité appel implique la configuration de l’infrastructure et l’installation du logiciel. La procédure suivante décrit le processus.
  
### <a name="deployment-steps"></a>Étapes de déploiement

1. Copier le CallQualityDashboard.msi sur l’ordinateur où le composant de base de données archive de CQD doit être installé (il s’agit de l’ordinateur sur lequel SQL Server installé). 
    
2. Exécutez le MSI (Windows vous invite à exécuter avec les privilèges d’administrateur, de le faire). 
    
3. Accepter le CLUF.
    
4. Sélectionnez le dossier de destination où les fichiers liés à des composants de tableau de bord qualité appeler seront situé ou acceptez l’emplacement par défaut.
    
5. Sélectionnez toutes les fonctions.
    
6. Dans la page Configuration de l’Archive QoE, fournissez les informations suivantes :
    
   - **Les mesures QoE SQL Server :** Nom de l’instance de SQL Server pour où se trouve la base de données de mesures QoE (il s’agit de la source de données).
    
   - **Nom de SQL Server QoE Archive :** Ce champ en lecture seule et fixe pour le nom de domaine complet de l’ordinateur local. Archivage de base de données peut être installé uniquement sur l’ordinateur local.
    
   - **QoE Archive SQL Server Instance :** Un nom d’instance SQL Server local pour lequel la base de données d’Archive doit être créé. Pour utiliser une instance de SQL Server par défaut, laissez ce champ vide. Pour utiliser une instance nommée de SQL Server, spécifiez le nom d’instance (par exemple, le nom après le "\").
    
   - **Base de données Archive de QoE :** Par défaut, cette option est définie à « Créer nouvelle base de données ». Étant donné que la mise à niveau de la base de données Archive n’est pas pris en charge, le seul cas dans lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données d’archivage existante a le même schéma que la génération doit être installé.
    
   - **De base de données de répertoire du fichier :** Chemin d’accès où les fichiers de base de données (.mdf et .ldf) pour la base de données d’archivage doivent être placés. Ce doit être sur un lecteur distinct (HDD2 dans la configuration matérielle recommandée) du système d’exploitation. Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide sans fichiers utilisé.
    
   - **Utilisation de plusieurs Partitions :** La valeur par défaut est défini sur « Partition plusieurs », ce qui nécessite une édition de Business Intelligence ou l’édition entreprise de SQL Server. Pour l’Édition Standard, l’option « Partition unique ». Notez que les performances de traitement de cube peuvent être affectés si la Partition unique est utilisée.
    
    > [!NOTE]
    > La sélection de l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée. Pour le modifier, le Cube doit être la première fonction désinstallé et réinstallé à l’aide de « modifier » dans le panneau de configuration. 
  
   - **Partition de répertoire du fichier :** Chemin d’accès où les partitions de la base de données Archive de QoE doivent être placées. Ce doit être sur un lecteur distinct (HDD3 dans la configuration matérielle recommandée) à partir du lecteur du système d’exploitation et le lecteur de fichiers de journal de base de données SQL. Notez que les noms de fichier sont corrigés dans l’installation, afin d’éviter tout conflit potentiel, il est recommandé qu’un répertoire vide sans fichiers utilisé.
    
   - **Utilisateur de travail de l’Agent SQL - nom d’utilisateur &amp; mot de passe :** Nom de compte de service de domaine et mot de passe (masqué) qui sera utilisé pour exécuter l’étape « Archive les données QoE » de la tâche de l’Agent de SQL Server (qui s’exécute la procédure stockée pour extraire les données de base de données de mesures QoE dans Archive de base de données, ce compte doit avoir accès en lecture à QoE métriques de base de données,  comme indiqué dans la section comptes. Ce compte doit également disposer d’une connexion dans l’Instance de SQL Server QoE Archive).
    
    > [!NOTE]
    > Le compte de l’instance de SQL Server sous lequel s’exécute, telles que NT SERVICE\MSSQLSERVER, doit avoir accès aux répertoires indiquées ci-dessus pour réussir l’installation. Pour plus d’informations, voir [Configurer des autorisations de système de fichiers pour l’accès au moteur de base de données](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Après avoir cliqué sur Suivant, le programme d’installation effectue les vérifications préalables et rapport si des problèmes sont rencontrés. Lorsque tous les pré-requis chèques passe, le programme d’installation passe à la page Configuration du Cube. 
    
    > [!NOTE]
    > Si le programme d’installation affiche un avertissement indiquant que le service SQL Server Agent pour l’instance de SQL Server Archive QoE n’est actuellement pas en cours d’exécution, l’installation peut se poursuivre, mais après l’installation, veuillez vous assurer que SQL Agent est en cours d’exécution et le type de démarrage de service Automatique afin que la tâche planifiée s’exécute. 
  
8. Dans la page de Configuration du Cube, fournissez les informations suivantes :
    
   - **Nom de SQL Server QoE Archive :** Ce champ en lecture seule et fixe pour le nom de domaine complet de l’ordinateur local. Cube peut être installé uniquement à partir de l’ordinateur qui contient la base de données Archive de QoE (Remarque. Cube proprement dit peut être installé sur un ordinateur distant. Voir ci-dessous)
    
   - **QoE Archive SQL Server Instance :** Nom de l’instance de SQL Server pour où se trouve la base de données Archive QoE. Pour spécifier une instance de SQL Server par défaut, laissez ce champ vide. Pour spécifier une instance nommée de SQL Server, entrez le nom d’instance (par exemple, le nom après le "\"). Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est prédéfinie avec la valeur fournie dans la page Configuration de l’Archive QoE.
    
   - **De cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour lequel le cube est créé. Ce peut être un autre ordinateur, mais l’utilisateur chargé de l’installation doit être un membre du groupe Administrateurs de serveur de l’instance de SQL Server Analysis Service cible.
    
    > [!NOTE]
    >  Pour plus d’informations sur la configuration des autorisations d’administrateur de serveur Analysis Services, voir [Accorder des autorisations administrateur du serveur (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Utilisation de plusieurs Partitions :** La valeur par défaut est défini sur « Partition plusieurs », ce qui nécessite une édition de Business Intelligence ou l’édition entreprise de SQL Server. Pour l’Édition Standard, l’option « Partition unique ». Notez que les performances de traitement de cube peuvent être affectés si la Partition unique est utilisée.
    
    > [!NOTE]
    >  La sélection de l’option d’utilisation de plusieurs Partitions ne peut pas être modifiée une fois l’installation terminée. Pour le modifier, le Cube doit être la première fonction désinstallé et réinstallé à l’aide de « modifier » dans le panneau de configuration.
  
   - **Utilisateur - nom d’utilisateur de cube &amp; mot de passe :** Nom de compte de service de domaine et mot de passe (masqué) qui déclenchera le traitement du cube. Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est préremplie avec la valeur fournie dans la page Configuration de l’Archive pour l’utilisateur de travail de l’Agent SQL, mais nous vous recommandons de spécifier un compte de service de domaine différent afin que le programme d’installation peut accorder le au moins le privilège requis pour l’il.
    
9. Lorsque vous cliquez sur Suivant, une autre série de validation est effectuée et que tout problème sera déclarée. En cas de réussite de la validation, le programme d’installation passe à la page Configuration du portail. 
    
10. Dans la page de Configuration du portail, fournissez les informations suivantes :
    
    - **De SQL Server QoE Archive :** Nom de l’instance de SQL Server pour où se trouve la base de données Archive de QoE. Notez que contrairement à la page de Configuration de l’Archive QoE et la page de Configuration du Cube, le nom de l’ordinateur n’est pas fixe et doit être fourni. Si le composant de QoE Archive a été sélectionné pour l’installation, ce champ est prédéfinie avec la valeur fournie dans la page Configuration de l’Archive QoE.
    
    - **De cube Analysis Server :** Nom de l’instance SQL Server Analysis Services pour où se trouve le cube. Si le composant de Cube a été sélectionné pour l’installation, ce champ est préremplie avec la valeur fournie dans la page Configuration du Cube.
    
    - **Référentiel SQL Server :** Nom de l’instance de SQL Server dans laquelle la base de données de référentiel doit être créé. Si le nom de l’instance de SQL Server pour où se trouve la base de données Archive de QoE a été fourni plus haut dans le programme d’installation (dans d’autres composants), ce champ est préremplie avec le nom d’instance QoE Archive DB SQL Server. Cela peut être n’importe quelle instance de SQL Server.
    
    - **Base de données de référentiel :** Par défaut, l’option est définie à « Créer nouvelle base de données ». Étant donné que la mise à niveau de la base de données de référentiel n’est pas pris en charge, le seul cas dans lequel l’option « Utiliser la base de données existante » peut être utilisée est si la base de données de référentiel existant a le même schéma que la génération doit être installé.
    
    - **Utilisateur du Pool d’applications IIS - nom d’utilisateur &amp; mot de passe :** Le pool d’applications IIS doit s’exécuter sous le compte. Les champs nom d’utilisateur et mot de passe seront grisés si les comptes du système intégré sont sélectionnés. Ces champs sont activés uniquement si « Autre » est sélectionné dans la liste déroulante afin que l’utilisateur puisse entrer les informations de compte de service de domaine.
    
11. Lorsque vous cliquez sur Suivant, l’arrondi final de la validation est effectué afin de garantir que les instances de SQL Server sont accessibles à l’aide des informations d’identification fournies et que IIS est disponible sur l’ordinateur. En cas de réussite de la validation, le programme d’installation poursuit l’installation. 
    
Lorsque le programme d’installation est terminé, très probablement le travail de l’Agent de SQL Server est en cours, en effectuant le chargement initial des données QoE et le traitement du cube. Selon la quantité de données QoE, le portail n’aura pas les données disponibles pour affichage encore. Pour vérifier l’état de la charge des données et le traitement du cube, accédez à `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Notez que l’URL de vérification de l’état du téléchargement de traitement de cube respecte la casse. Si vous entrez « santé » l’URL ne fonctionne pas. Vous devez entrer « Santé » à la fin de l’URL avec une majuscule H. 
  
Messages du journal détaillée seront affiche si le mode débogage est activé. Pour activer le mode débogage, accédez à **%SYSTEMDRIVE%\Program Files\Skype pour le CQD\QoEDataService\web.config Business 2015**et mettre à jour la ligne suivante afin que la valeur est définie sur **True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

La page principale du portail est accessible via `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Gestion de l’accès de l’utilisateur pour le portail

Gérez les autorisations utilisateur sur le portail, nous recommandons à l’aide de l’autorisation d’URL, ce qui a été introduit dans IIS 7.0. Pour plus d’informations sur la sécurité IIS, reportez-vous à la section [Présentation IIS 7.0 l’autorisation d’URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Toutes les applications web ou site web héritent par défaut configuré pour l’ensemble IIS, qui est généralement de « Autoriser tous les utilisateurs » l’autorisation d’URL. Si l’accès au portail doit être plus restrictif, puis les administrateurs peuvent accorder l’accès pour seulement le groupe d’utilisateurs spécifique en modifiant les « règles d’autorisation ».
  
![Déployer la qualité des appels - règles d’autorisation dans IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> L’icône de règles d’autorisation est à ne pas confondre avec l’autorisation « .NET » dans la section d’ASP.NET, qui est un mécanisme d’autorisation différents. 
  
Les administrateurs doivent d’abord supprimer la règle héritée « autoriser tous les utilisateurs ». Cela empêche les utilisateurs non autorisés d’accéder au portail.
  
![Déployer CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Ensuite, les administrateurs doivent ajouter de nouvelles règles Autoriser et donner à des utilisateurs spécifiques l’autorisation pour accéder au portail. Il est recommandé qu’un groupe local appelé « CQDPortalUsers » est créé pour gérer les utilisateurs.
  
![Déployer le Tableau de bord de la qualité des appels](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Les détails de configuration sont stockés dans le fichier web.config situé dans le répertoire physique du portail.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

L’étape suivante consiste à configurer le tableau de bord de la CQD. Une fois que les utilisateurs sont authentifiés par IIS, ils doivent disposer d’autorisations sur le répertoire CQD pour accéder au contenu de portail web. Il est possible de modifier les listes ACL par le biais de l’onglet sécurité des propriétés du répertoire CQD pour ajouter des utilisateurs individuels ou des groupes ; Toutefois, l’approche recommandée consiste à laisser les autorisations de fichiers inchangés. Au lieu de cela, modifiez le paramètre IIS pour utiliser le processus de travail IIS pour accéder au répertoire CQD quel utilisateur est authentifié. 
  
> [!IMPORTANT]
> Il est important de ne modifier ce paramètre pour l’application de CQD et non pour les deux applications API : QoEDataService et QoERepositoryService. 
  
### <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configuration de l’accès de fichier pour le CQD (tableau de bord)

1. Ouvrez l’éditeur de Configuration de CQD.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Sous la Section, choisissez **system.webServer/serverRuntime**.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Remplacez authenticatedUserOverride par **UseWorkerProcessUser**.
    
     ![Déployer le Tableau de bord de la qualité des appels - Éditeur de configuration](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Cliquez sur **Appliquer** dans la partie droite de la page.
    
## <a name="known-issues"></a>Problèmes connus

Dans de rares cas, le programme d’installation ne peut pas créer les paramètres appropriés dans IIS. Modification manuelle est nécessaire pour permettre aux utilisateurs de se connecter à la CQD. Si les utilisateurs rencontrent des problèmes de connexion, procédez comme suit :
  
1. Ouvrir le Gestionnaire des services Internet haut et accédez au Site Web par défaut.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Cliquez sur « Authentification ». Si le « Anonyme », « L’emprunt d’identité ASP.NET », « Authentification par formulaire » et « Authentification Windows » ne correspondent pas les paramètres présentés ci-dessous, les changer manuellement pour faire correspondre les paramètres ci-dessous. Tous les autres mécanismes d’authentification doivent être désactivés.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Pour « Authentification Windows », cliquez sur Paramètres avancés sur le côté droit.
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Accepter la valeur « Protection étendue » et cochez la case « authentification du mode noyau activer ».
    
     ![Déployer le Tableau de bord de la qualité des appels](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Répétez les étapes ci-dessus pour chacune des entrées ci-dessous « Site Web par défaut » « CQD », « QoEDataService » et « QoERepositoryService ».
    
Pour les liaisons de port HTTP et HTTPS le programme d’installation va créer des liaisons de port sur les numéros de port par défaut (port 80 pour HTTP) et le port 443 pour HTTPS. S’il existe un autre site Web sur l’ordinateur qui utilise ces liaisons, il y aura un conflit et il est impossible de prédire le comportement d’IIS. La meilleure façon d’éviter ce problème est de s’assurer qu’aucun autre site Web n’est mappés sur les ports 80 et 443 avant d’installer CQD. 
  
Pour activer le protocole SSL/TLS dans IIS et forcer les utilisateurs à se connecter via le protocole HTTPS sécurisé au lieu de HTTP :
  
1. Configurer le protocole SSL (Secure Sockets Layer) dans IIS, consultez [Configuration de SSL dans IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Une fois fait, remplacez `http` avec `https`.
    
2. Pour obtenir des instructions sur l’activation de TLS dans les connexions SQL Server, voir [comment activer le cryptage SSL pour une instance de SQL Server à l’aide de Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).
    
### <a name="cube-sync-fails"></a>Échec de la synchronisation de cube

QoEMetrics peut contenir des enregistrements non valides selon les horloges de l’utilisateur final. Si le délai maximal autorisé est supérieur à 60 ans, l’importation de cube échoue.
  
 Vérifiez les Min et Max début/fin, à l’aide des sélections ci-dessous. Recherche et suppression d’enregistrements dans le futur dépassée et très éloigné, ils peuvent ne pas être et qu’ils seront diviser les processus de synchronisation.
  
- Sélectionnez MIN(StartTime) à partir de CqdPartitionedStreamView
    
- Sélectionnez MAX(StartTime) à partir de CqdPartitionedStreamView
    
- Sélectionnez MIN(EndTime) à partir de CqdPartitionedStreamView
    
- Sélectionnez MAX(EndTime) à partir de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tâches après installation

### <a name="importing-buildings-and-networks"></a>Importation des bâtiments et des réseaux

Après l’installation de CQD, effectuez les tâches de configuration suivantes :
  
1. Définir des types de construction (recommandés)
    
2. Définir les types de propriété de construction (recommandés)
    
3. Définir les types de réseau (recommandés)
    
4. Bâtiments d’importation (recommandé)
    
5. Importation des sous-réseaux (recommandés)
    
### <a name="define-building-types"></a>Définir des Types de construction

Types de construction sont utilisés pour décrire les définitions de bâtiments différents types au sein de votre organisation. 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
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

Les types de propriété sont utilisés pour distinguer les actifs loués vs détenus.
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Exemples
  
- Contoso louées non-RE&amp;F
    
- Contoso louées RE&amp;F
    
- La propriété de Contoso
    
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
  
### <a name="define-network-names"></a>Définir des noms de réseau

Types de réseau sont utilisés pour décrire les différents types de réseaux au sein de l’organisation. Cela vous donne la possibilité de filtrer (ou isoler) les Types de réseau spécifiques.
  
> [!NOTE]
> Il est vivement recommandé de définir les noms de réseau, mais elle est facultative. Si vous décidez de ne définit ne pas de noms de réseau, assurez-vous que le chaque entrée CqdNetwork a un BuildingId de 0. 
  
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

Les paramètres NetworkNameID et NetworkName sont requis, le paramètre NetworkType est facultative, mais recommandée.
  
### <a name="import-buildings"></a>Bâtiments d’importation

Importation de bâtiments vous donne la possibilité d’obtenir création d’analyses spécifiques (appels médiocres par construction sur WiFi/câblé, etc.).. 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Avant d’importer une nouvelle génération vous disposez déjà d’un BuildingKey prédéfini identifié. Pour ce faire, émettez la commande « Sélectionner les MAX(BuildingKey) de CqdBuilding » SQL pour identifier la valeur actuelle et ajoute 1 au résultat.
  
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

Le BuildingKey BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId des paramètres sont requis, les autres paramètres sont facultatifs.
  
### <a name="import-subnets"></a>Importer des sous-réseaux

Importation de bâtiments vous donne la possibilité d’obtenir création d’analyses spécifiques (appels médiocres par construction sur WiFi/câblé, etc.).. 
  
> [!NOTE]
> Cette étape est facultative, mais recommandée. 
  
Importer des sous-réseaux et de les mapper aux bâtiments importés dans la dernière étape. Si vous décidez de ne pas remplir NetworkName, assurez-vous que chaque entrée de ce tableau utilise un NetworkNameID de 0.
  
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

Remplissage des informations de BSSID vous donne corrélation de flux WiFi supplémentaire par le contrôleur ou radio. C’est en plus du filtrage par bâtiment ou par sous-réseau. 
  
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

**Détails de la CqdBssidTable**

|**Comme illustré à la CQD**|**Table de CQDBssid**|**Entrées de l’exemple**|
|:-----|:-----|:-----|
|PA Name  <br/> |POINT D’ACCÈS  <br/> |POINT D’ACCÈS 1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (vous devez utiliser le format délimité)  <br/> |
|Contrôleur de  <br/> |Bâtiment  <br/> |Aruba PA 7  <br/> |
|DISPOSITIF  <br/> |ess  <br/> |: Contrôleur1  <br/> |
|Radio  <br/> |phy  <br/> |BGN  <br/> |
   
### <a name="processing-the-imported-data"></a>Traitement des données importées

Par défaut, après avoir importé les données de construction ou le réseau qu’il s’applique uniquement aux enregistrements générés après ce point dans le temps. 
  
Pour marquer tous les enregistrements précédents avec ces nouvelles données, vous devrez exécuter la procédure stockée de CqdUpdateBuilding comme indiqué ci-dessous : 
  
Lui donner la date de votre premier enregistrement (identifier à l’aide de la commande Sélectionner le MIN(StartTime) à partir de SQL CqdPartitionedStreamView), une date de fin de demain, puis vide pour les deux dernières valeurs.
  
Une fois les données sont associées à des données de flux de données, le Cube SSIS doit retraiter tous les enregistrements. Cela s’applique également lorsque en bloc de l’ajout de données BSSID/fournisseur de services Internet. Assurez-vous que « Procédure complet » est sélectionné.
  

