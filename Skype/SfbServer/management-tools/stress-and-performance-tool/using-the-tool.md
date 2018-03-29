---
title: À l’aide de la Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Pour exécuter le Skype pour Business Server 2015 Stress et l’outil performances, vous avez besoin pour être en mesure de gérer des utilisateurs, des contacts et des profils utilisateur, configurer l’outil pour l’exécution et puis passez en revue la sortie ou les résultats qui sont générés par l’outil.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>À l’aide de la Skype pour Business Server 2015 Stress et l’outil performances
 
Pour exécuter le Skype pour Business Server 2015 Stress et l’outil performances, vous avez besoin pour être en mesure de gérer des utilisateurs, des contacts et des profils utilisateur, configurer l’outil pour l’exécution et puis passez en revue la sortie ou les résultats qui sont générés par l’outil.
  
Il existe quatre domaines impliqués dans l’exécution du Skype pour Business Server 2015 Stress et l’outil de Performance (le fichier exécutable est LyncPerfTool.exe) :
  
- [Créer des utilisateurs et des Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurer le profil de l’utilisateur](using-the-tool.md#BKMK_UserProfile)
    
- [Exécutez LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interprétation des résultats](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Créer des utilisateurs et des Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

Vous devez utiliser le Skype pour l’outil de mise en service des utilisateurs Business Server 2015 (SB 2015) (UserProvisioningTool.exe) pour créer des utilisateurs et des contacts pour votre contrainte et les tests de performances.
  
Il s’agit d’une liste de termes utiles qui peut s’avérer utile lorsque vous lisez les rubriques :
  
- **Unité d’organisation** , unité d’organisation de l’Active Directory Domain Services (AD DS) (OU).
    
- **Fédéré / Cross Pool** - les utilisateurs peuvent communiquer avec les utilisateurs d’autres services de messagerie instantanée (IM).
    
- **Les listes de distribution** - ou listes de distribution. Il s’agit d’objets dans les services AD DS qui contient une liste d’utilisateurs de domaine Active Directory. Ils sont utilisés pour faciliter les communications entre des groupes de personnes.
    
- **Service d’informations de localisation** - le Skype pour le service Business Server 2015 qui, lorsqu’elle est activée et configurée par téléphone, permet la récupération de l’emplacement physique pour les services E911 (Enhanced 911).
    
- **Les numéros de téléphone aux États-Unis** , les numéros de téléphone attribués à l’utilisateur, en plus de l’URI SIP qui est utilisé pour le routage des appels entrants et sortants dans recherche de numéro inversée (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des Contacts à l’aide de UserProvisioningTool.exe

> [!NOTE]
> Avant même de commencer, être absolument certain que vous êtes connecté en tant que membre du groupe de sécurité Admins du domaine pour exécuter cet outil. Vous devez pour ce faire, dans la mesure où vous allez créer des utilisateurs Active Directory. 
  
Vous devez utiliser le Skype pour l’outil de configuration des utilisateurs Business Server pour créer des utilisateurs et des contacts pour la simulation de charge.
  
Le **Skype pour l’outil de configuration des utilisateurs Business Server** est installé avec le package **Skype pour Business Server Stress et l’outil performances** . N’oubliez pas que le programme d’installation de package (CapacityPlanningTool.msi) a été exécuté sur le serveur frontal ou le serveur Standard Edition que vous souhaitez tester.
  
Vous pouvez démarrer le Skype pour l’outil de configuration des utilisateurs Business Server en exécutant le fichier UserProvisioningTool.exe (situé dans % InstalledDirectory%LyncStressAndPerfTool\LyncStress) sur le serveur frontal ou le serveur Standard Edition.
  
> [!IMPORTANT]
> Lorsque vous créez un grand nombre d’utilisateurs (par exemple, 10 000 ou plus), exécute le UserProvisioningTool.exe. Vous devez effectuer cette opération car l’outil sera création et configuration des utilisateurs de *nouvelle* annonce.
  
Lorsque l’outil de configuration utilisateur s’ouvre, cliquez sur Configuration et sélectionnez la Configuration de la charge. 
  
Pour commencer la configuration des utilisateurs et des contacts, chargez le fichier par défaut inclus dans le package, appelé « SampleData.xml ». Cela sera prérempli champs avec les données d’exemple dont vous aurez besoin de modifier les rendra pertinentes pour votre déploiement.
  
Si vous avez un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, vous pouvez charger ce fichier à la place. Renseignez les champs dans l’outil de mise en service d’utilisateur, comme décrit dans les sections ci-dessous.
  
### <a name="to-configure-server-options"></a>Pour configurer les options de serveur

1. Dans le champ **Avant fin Pool de nom de domaine complet** , tapez le nom de domaine complet (FQDN) du serveur Standard Edition server ou le pool frontal dans lequel vous souhaitez héberger des utilisateurs.
    
2. Dans le champ **Préfixe de nom d’utilisateur** , tapez le préfixe que vous souhaitez utiliser pour bust les noms d’utilisateur pour des tests (par exemple, « TestUser »).
    
3. Dans le champ **mot de passe** , tapez un mot de passe qui sera utilisé sur tous les comptes d’utilisateurs de test.
    
4. Dans le champ **Domaine du compte** , tapez le nom de domaine de votre domaine Active Directory actuel (celui dans lequel vous souhaitez créer des utilisateurs de test).
    
5. Dans le champ **Unité d’organisation** , tapez le nom du domaine Active Directory où vous souhaitez créer ces utilisateurs de test. (Si l’unité d’organisation n’existe pas déjà, il vous est créé pour vous).
    
6. Dans le champ de **l’indicatif régional** , tapez l’indicatif à trois chiffres pour être utilisé sur tous les comptes utilisateur de test. Assurez-vous que le code de zone que vous avez choisi n’entre pas en conflit avec les codes de zone d’autres utilisateurs dans Active Directory.
    
7. Activez la case à cocher **Vocal activé** , si vous souhaitez activer les utilisateurs de test de Voix Entreprise.
    
8. Dans le champ **Nombre d’utilisateurs** , donnez le nombre total d’utilisateurs de test que vous souhaitez créer.
    
9. Dans le champ **Démarrer l’Index** , donnez le numéro de départ qui vous servir d’un suffixe pour le préfixe de nom d’utilisateur (par exemple, le préfixe est « TestUser », et le prénom se termine par « 0 » dans l’exemple ci-dessous.)
    
     ![Outil d’affectation d’utilisateurs affichant l’onglet Création d’utilisateur.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Créer le bouton utilisateurs

Lorsque vous cliquez sur le bouton **Créer les utilisateurs** , les paramètres d’entrée que vous avez entrées sont validées. S’il existe des erreurs de validation, vous devrez faire pour les corriger. Ou, si toutes les valeurs sont correctes, les utilisateurs seront commencent à apparaître dans Active Directory (dans quelle unité d’organisation spécifiée). Vous verrez une barre de progression en bas de l’outil en cours d’exécution. Ne fermez pas l’application pendant que la barre de progression est active.
  
Création de l’utilisateur prend du temps, veuillez plan en conséquence. Ce processus peut prendre de quelques minutes à quelques utilisateurs, quelques heures pour un grand nombre d’utilisateurs.
  
Si vous n’avez pas accès au contrôleur de domaine Active Directory dans votre environnement de test, vous pouvez toujours valider la création de l’utilisateur en se connectant en tant qu’un des utilisateurs dans la plage d’utilisateurs que vous avez spécifié pour créer. N’oubliez pas d’utiliser le préfixe et le suffixe, ainsi que de la @sipDomain le nom d’utilisateur. Voici un exemple : *TestUser20@contoso.net* .
  
> [!NOTE]
> Si les utilisateurs existent déjà, cliquez sur le bouton Créer des utilisateurs les mettra à jour avec les modifications de configuration. 
  
#### <a name="delete-users-button"></a>Supprimer le bouton utilisateurs

Lorsque vous cliquez sur le bouton **Supprimer les utilisateurs** , les paramètres d’entrée de l’onglet seront validées. S’il existe des erreurs de validation, vous serez invité à les corriger, et si les valeurs d’entrée sont correctes, les utilisateurs de test spécifié seront désactivés et supprimés d’Active Directory. Là encore, une barre de progression s’affiche au bas de cet onglet et vous ne doit pas fermer l’application alors que la barre de progression est active.
  
> [!NOTE]
> Seuls les numéros de téléphone au format américain sont pris en charge. Numéros de téléphone sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool.exe sont activés par défaut pour les Voix Entreprise. Les scénarios qui utilisent le numéro de téléphone, de Standard automatique de conférence ou des appels de communications unifiées-PSTN, utilisent ce numéro de téléphone pour acheminer correctement les appels. Pour cette raison, *chaque utilisateur* doit avoir un *numéro de téléphone unique* .
  
> [!NOTE]
> **Si vous devez créer les utilisateurs deux fois, la commande échouera, sauf si vous utilisez un indicatif régional différent, ou si les utilisateurs précédentes ont été désactivés à l’aide de l’applet de commande Disable-CsUser.**
  
> [!IMPORTANT]
> Avant de créer des contacts, vous devez d’abord terminer la réplication de l’utilisateur (qui est effectuée à partir de l’onglet utilisateurs). 
  
> [!IMPORTANT]
> Si vous venez de créer vos utilisateurs, vous devez attendre que Skype pour la réplication de serveur de l’entreprise se termine et remplit les comptes d’utilisateurs dans la base de données. **Si les utilisateurs n’ont pas terminé la réplication, vous verrez une erreur.** Vous saurez que lorsque les utilisateurs aient terminé la réplication si la Skype pour service d’entreprise serveur 2015 Front-End a démarré ou en correctement en exécutant l’applet de commande Get-CsUser sur le dernier utilisateur le nombre total spécifié.
  
#### <a name="contacts-creation-tab"></a>Onglet Création de contacts

Cet onglet vous permet de vous fournir les informations de contacts des utilisateurs pour votre test.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de contenu.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Pour configurer les contacts de l’utilisateur, effectuez les opérations suivantes :

1. Dans le champ **Moyenne de Contacts par utilisateur** , entrez le nombre de contacts dans des listes de contacts pour chaque utilisateur.
    
2. Activez la case à cocher **fixe** si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous souhaitez faire varier le nombre de contacts créés pour les utilisateurs, désactivez cette case à cocher.
    
3. Dans le champ **Groupes de Contact moyenne par utilisateur** , entrez le nombre de groupes de contacts par utilisateur. Ce nombre doit être inférieur à la **Moyenne de Contacts par utilisateur**.
    
4. Dans le champ **fédéré / Cross pourcentage Contacts de Pool** , fournir un nombre compris entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.
    
5. Dans le champ **fédéré / Cross préfixe utilisateur de Pool** , donnez le nom d’utilisateur pour les utilisateurs fédérés qui seront ajoutés à la liste de contacts des utilisateurs locaux.
    
6. Dans le champ **fédérée / domaine SIP de l’utilisateur Pool de Cross** , donnez le nom de domaine SIP des utilisateurs fédérés.
    
7. Dans l’onglet **Création d’utilisateur** , assurez-vous que les informations sont correctes. Vos contacts seront créés à partir des valeurs dans l’onglet Création d’utilisateur.
    
8. Cliquez sur **Créer des Contacts** pour commencer la création du contact. Ce processus peut prendre plusieurs minutes. Une fois terminée, une boîte de dialogue s’affiche avec le message, « opération terminée avec succès. » Vous pouvez valider les contacts qui ont été créés en ouvrant une session en tant qu’utilisateur qui a été créé à partir de l’onglet Création d’utilisateur.
    
> [!NOTE]
> Une fois les contacts créés, cet outil va redémarrer tous les serveurs frontaux dans le pool cible. Il peut prendre plus longtemps (jusqu'à 2 heures) pour les serveurs frontaux Démarrer, en fonction du nombre de contacts ont été créé par cette opération. 
  
#### <a name="distribution-list"></a>Liste de distribution

Le Skype pour Business Server 2015 Stress et l’outil performances permet de simuler la fonctionnalité d’extension de la liste de Distribution (DL) dans le Skype pour client d’entreprise 2015. Vous pouvez ignorer cette étape si vous ne souhaitez pas activer l’expansion de liste de distribution dans l’outil de configuration des utilisateurs.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de liste de distribution.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
L’onglet liste de Distribution vous permet de créer des listes de distribution qui utilisent le Stress et l’outil de performances pour la fonction d’extension de liste de Distribution. Avant de créer des listes de distribution, Skype pour Business Server 2015 doit être déployé, y compris les ayant exécuté ForestPrep. Si ce n’est pas le cas, les attributs de la liste de distribution n’existera pas dans le schéma Active Directory, afin que l’outil ne sera pas en mesure de créer des listes de distribution.
  
### <a name="to-configure-distribution-lists"></a>Pour configurer les listes de Distribution :

1. Dans le champ **Nombre de listes de Distribution** , fournir le nombre total de listes de distribution à créer (la recommandation ici est que vous démarrez avec une valeur qui est le double du nombre d’utilisateurs que vous avez.).
    
2. Dans le champ **Préfixe de liste de Distribution** , entrez un préfixe ayant toutes les listes que vous créez, par exemple *testDL* . En d’autres termes, à 100 listes de distribution, les noms de votre liste de distribution ressemblera : testDL0, testDL1, jusqu'à testDL99.
    
3. Dans le champ **Minimum de membres dans une liste de distribution** , entrez le nombre minimal d’utilisateurs de placer dans chaque liste de distribution.
    
4. Dans le champ **Nombre maximal de membres dans une liste de distribution** , entrez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.
    
#### <a name="create-distribution-lists-button"></a>Créer des listes de Distribution de bouton

Lorsque vous cliquez sur le bouton Créer des listes de Distribution, l’outil interroge Active Directory pour voir si les listes de distribution correspondant que le préfixe et le numéro existe déjà. L’outil crée les listes de distribution qui n’existent pas déjà. Lorsque vous ajoutez des membres à ces nouveaux des listes de Distribution, il vous choisissez les utilisateurs à partir de la plage spécifiée sous l’onglet Création d’utilisateur.
  
#### <a name="location-info-service-config-tab"></a>Onglet de configuration de Service d’informations d’emplacement

Le Skype pour Business Server 2015 Stress et l’outil de Performance peut également générer des fichiers de configuration factice pour le Service d’informations d’emplacement. Notez que le Service d’informations de localisation en général ne réduire considérablement les performances sur les serveurs. 
  
![Outil d’affectation d’utilisateurs affichant l’onglet Configuration du service Informations d’emplacement.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si vous choisissez de ne tester cette fonctionnalité, renseignez les valeurs dans le formulaire et cliquez sur le bouton Générer des fichiers de configuration LIS, qui va créer. Fichiers CSV appelés :
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Pour importer ces fichiers dans la base de données LIS utilisent ces applets de commande PowerShell :
  
- Ensemble-CsLisSubnet
    
- Ensemble-CsLisSwitch
    
- Ensemble-CsLisPort
    
- Ensemble-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurer le profil de l’utilisateur
<a name="BKMK_UserProfile"> </a>

Une fois que vos utilisateurs sont créés (par l’intermédiaire de l’outil de création d’utilisateur), vous pouvez configurer les profils utilisateur avec le Skype pour l’outil de Configuration de charge 2015 Business Server (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Le Skype pour l’outil de Configuration de charge 2015 Business Server en cours d’exécution

Démarrez l’outil de Configuration de charge (UserProfileGenerator.exe) et renseignez les onglets. Cet outil crée un répertoire pour chaque client que vous aurez besoin pour exécuter des simulations de vos ordinateurs. Chaque répertoire de client est fourni avec un script pour démarrer le Skype Business Server 2015 Stress et l’outil performances (LyncPerfTool.exe). Les sections ci-dessous donnera des exemples montrant comment renseigner les champs de chaque onglet de la Skype pour l’outil de Configuration de charge Business Server 2015.
  
> [!IMPORTANT]
> Les valeurs spécifiques à l’utilisateur de l’outil de Configuration de charge (UserProfileGenerator.exe) doivent correspondre les valeurs spécifiées dans le Skype pour outil de création de Business Server 2015 utilisateur (UserProvisioningTool.exe) pour le pool. 
  
#### <a name="common-configuration-tab"></a>Onglet de Configuration commun

L’onglet de **Configuration courante** de l’outil de Configuration de charge est indiqué ci-dessous. Renseignez les champs de l’onglet Configuration courante, comme décrit dans les étapes suivantes.
  
![Onglet Affectation d’utilisateurs affichant l’onglet Configuration courante.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Dans le champ **Nombre de Machines disponibles** , tapez le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter l’outil de Stress et de performances (LyncPerfTool.exe). Nous vous recommandons que vous disposez d’un ordinateur pour chaque 4500 utilisateurs que vous allez être simulation, mais ce nombre peut varier si vous réduisez le niveau de charge, ou que vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles de l’outil (niveaux de charge sont définis dans l’onglet Général des scénarios).
    
2. Dans le champ **préfixe pour les noms d’utilisateur** , entrez un préfixe pour le champ de nom d’utilisateur de tous les utilisateurs. Pour ouvrir une session dans l’identificateur de ressource uniforme (URI) sera : *UserPrefix [Démarrer Index utilisateur... (Nombre d’utilisateurs-1)] @User domaine* , par exemple, myUser009@Contoso.com.
    
3. Dans le champ **mot de passe pour tous les utilisateurs** , entrez le mot de passe utilisé lors de la création des utilisateurs. Si vous ne renseignez pas ce champ le nom d’utilisateur sera défini comme le mot de passe.
    
4. Dans le champ **d’Index de démarrage utilisateur** , saisissez l’index du premier utilisateur à configurer. Vous pouvez configurer des plages différentes pour différents types ou niveaux de charge, mais vous devez exécuter l’outil de Configuration de charge (UserProfileGenerator.exe) par la plage que vous souhaitez configurer.
    
5. Dans le champ **Nombre d’utilisateurs** , entrez le nombre total d’utilisateurs que vous souhaitez configurer.
    
6. Dans le champ **Domaine de l’utilisateur** , entrez le domaine utilisé pour l’URI SIP. Cela est utilisé pour construire l’URI SIP de chaque utilisateur à ouvrir une session sur le Skype pour serveur Business Server 2015 serveur frontal ou Standard Edition et peut être différent du domaine de compte.
    
7. Dans le champ **Compte de domaine** , entrez l’ouverture de session de domaine AD DS.
    
8. Dans le champ **Pourcentage de MPOP** (pourcentage de plusieurs Point of Presence), donnez une valeur pour le pourcentage d’utilisateurs qui sont connectés à partir de plusieurs ordinateurs ou périphériques, par exemple, 10 pour cent.
    
9. Entrez le nombre maximal de points de terminaison simultanées dans le champ de **connexion par seconde (par Instance)** . Il s’agit de la valeur maximale nombre d’ouvertures de session pour les utilisateurs, et la recommandation est un taux inférieur à / égal à 2 par seconde (< = 2).
    
10. Dans le champ **Proxy d’accès ou le nom FQDN du Pool** , entrez le nom de domaine pleinement qualifié (FQDN) du serveur que vous souhaitez que les clients pour se connecter à. Si les utilisateurs sont connectés en externe, vous devrez taper le proxy d’accès. Si les utilisateurs sont internes, donnez le nom de domaine complet de leur serveur Pool d’entreprise ou Standard Edition.
    
11. Dans le champ **Port** , entrez le port que vous souhaitez que les utilisateurs utilisent pour SIP (ici la valeur par défaut est 5061).
    
12. Pour le champ **Paramètres de serveur de réseau externe** , attribuez le Proxy d’accès ou FQDN du Pool et, à nouveau, le **Port**. Ces paramètres sont utilisés uniquement pour la simulation de charge de points de terminaison externe.
    
#### <a name="general-scenarios-tab"></a>Onglet de scénarios de général

![Chargez l’outil de configuration affichant l’onglet Scénarios généraux.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Vous pouvez configurer les niveaux de charge et les paramètres pour chacun des scénarios généraux offerts par la détermination de ce que vous voulez exécuter ou le laisser désactivé. Voici vos options générales :
  
> [!NOTE]
> Valeurs de niveau de charge de tous les champs, mais les Services d’informations locales sont **désactivés**, **faible**, **moyen**, **élevé**ou **personnalisé**. Si vous sélectionnez n’importe quel paramètre mais désactivé, les configurations sont générées pour chaque client. Élevé se traduit par la charge maximale prise en charge sur le serveur ; moyen est de 60 % de la charge élevée ; faible est de 30 %. 
  
- **Messagerie instantanée-** Cela inclut le peer-to-peer et conférence ; Sélectionnez la valeur appropriée pour le niveau de charge.
    
- **Conférence audio-** Choisissez un niveau de charge de conférence audio *uniquement* . Appels de peer-to-peer seront traités un peu plus tard dans la section **Scénarios de voix** . Ouvrez l’onglet **Options avancées** pour activer MultiView.
    
- **Partage d’applications-** Choisissez un niveau de charge pour le partage d’application.
    
- **Collaboration de données-** Choisissez un niveau de charge de la collaboration de données, qui inclut le service Conférence de données.
    
- **Extension des listes de distribution :** Cliquez sur le bouton **Avancé** et renseignez le champ avec les mêmes valeurs configurées dans l’onglet liste de distribution de l’outil de création d’utilisateur (UserProvisioningTool.exe). Choisissez un niveau de charge.
    
- **Adresse carnet Web requête-** Il s’agit du service de recherche de carnet d’adresses plutôt que le téléchargement de fichiers de carnet d’adresses. Si vous souhaitez activer pour les téléchargements de fichiers du carnet d’adresses, cliquez sur le bouton **Avancé** et que vous définissez **EnableABSDownload** à True. Donner une valeur de niveau de charge.
    
- **De Service Response Group-** Cliquez sur le bouton **Avancé** et spécifiez les URI des groupes de réponse vous déjà créé lors du déploiement d’agents de Service Response Group. Vous devez choisir au moins un groupe de réponse. Pour utiliser plusieurs, séparer les groupes de réponse avec des points-virgules. Mise à jour **RGSUriSuffixStartIndex** et **RGSUriSuffixEndIndex** à des valeurs réelles. Choisissez un niveau de charge.
    
- **Services d’informations de localisation-** Sélectionnez un niveau de charge soit activé ou désactivé.
    
> [!NOTE]
> Chacun des scénarios a un bouton Avancé situé à côté d’elle et un ensemble de cases à cocher qui permettent à des variations de la valeur par défaut. 
  
- Choix *d’Ad hoc* permettra l’outil générer la simulation de conférences qui va être créé dans l’ensemble de l’heure.
    
- Si vous choisissez de *Grande Conf* signifie qu’un grand scénario conférence sera simulé.
    
-  *Externe* indique à l’outil également simuler les utilisateurs externes.
    
Ces cases à cocher et les boutons sont des valeurs supplémentaires spécifiques à chaque scénario et va modifier le comportement de l’outil de performances et le Stress et permettent la personnalisation.
  
Pour chaque scénario sous l’onglet Général des scénarios (à l’exception des Services d’informations de localisation), si la valeur du niveau de charge est **personnalisé**, puis la conversation taux est calculé à l’aide du champ correspondant dans la boîte de dialogue Paramètres avancés. Le nom de champ peut varier selon le scénario, mais la description du champ indique : *Remarque Ce nombre servira uniquement si personnaliser est sélectionné dans le menu déroulant* .
  
Les valeurs **haute**, **moyenne**et **basse**, modifier les taux de conversation par modalité dans le modèle d’utilisateur qui est un solde de tous les scénarios. S’il est nécessaire pour modifier le niveau de charge par modalité en raison d’une différence d’utilisation attendue, utilisez un taux de conversation personnalisée.
  
#### <a name="voice-scenarios-tab"></a>Onglet de scénarios de voix

Il s’agit de l’onglet de configuration de tous vos scénarios liés à la voix.
  
![Chargez l’onglet Scénarios vocaux de l’outil de configuration.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Vos options sont les suivantes :
  
- **VoIP :** Cliquez sur le bouton **Avancé** et ajoutez les valeurs des champs PhoneAreaCode et LocationProfile (plan de numérotation). Vous y trouverez également une valeur de niveau de charge. Si vous choisissez un niveau de charge de VoIP ou passerelle de communications unifiées/RTC activé, puis un réseau téléphoniques publics commutés (RTPC) pour les communications unifiées (CU) fichier de configuration sera généré pour simuler des appels externes.
    
- **Passerelle de communications unifiées/RTPC-** Vous devez choisir une valeur de niveau de charge, et lorsque vous choisissez n’importe quoi autre que désactivé, vous disposez également de fournir une valeur pour le code de zone RTPC en cliquant sur le bouton **Avancé** . Cliquez sur **Ajouter** sous le serveur de médiation et le RTPC. Vérifiez que vous avez un itinéraire configuré pour le code de la zone.
    
    > [!TIP]
    > Vous pouvez utiliser soit le Skype pour panneau de Business ou Skype pour Business Management Shell pour vérifier votre configuration de routage voix. 
  
- **Intendant-** Fournir une valeur pour le niveau de charge. Toute valeur autre que désactivé Active le champ **Numéro de téléphone** . Entrez le numéro de téléphone de la Standard automatique que vous souhaitez utiliser. Cliquez sur **Avancé** et fournir une valeur pour le champ **LocationProfile** .
    
- **Appelez le Service de stationnement-** Dans ce cas, fournir un niveau de charge.
    
- **Serveur de médiation et RTPC-** Chaque serveur de médiation que vous souhaitez utiliser a besoin de son propre simulator RTPC. Une fois que vous avez déterminé le client que vous allez utiliser pour le simulateur, configuration de votre serveur de médiation pour acheminer à cet ordinateur sur le simulateur RTPC vous appelle configuré. Cliquez sur le bouton **Ajouter** pour configurer une valeur pour le serveur de médiation.
    
    > [!NOTE]
    > Chaque scénario a un bouton Avancé situé en regard de celui-ci. Boîtes de dialogue avancées contiennent des paramètres spécifiques pour chaque scénario de modifient le comportement de l’outil de performances et le Stress et activer la personnalisation. > Pour chaque scénario sous l’onglet scénarios vocaux, si la valeur du niveau de charge est **personnalisé**, puis le taux de conversation est calculé par à l’aide du champ correspondant dans la boîte de dialogue Paramètres avancés. Le nom de champ peut varier selon le scénario, mais la description du champ indique : *Remarque Ce nombre servira uniquement si personnaliser est sélectionné dans le menu déroulant* .
  
#### <a name="web-app-tab"></a>Onglet de l’application Web

![Chargez l’onglet Application web de l’outil de configuration.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web application prend en charge les scénarios de conférence via le serveur Unified Communications Web API (UCWA) qui est installé sur un serveur frontal. Utilisez l’onglet Web App pour configurer tous les scénarios d’axées sur l’application web. Les options sont :
  
- **Paramètres généraux de l’application Web-** Cliquez sur le bouton **Paramètres supplémentaires** et définir la **ReachTargetServerUrl** pour le Pool de répertoire virtuel IP (VIP) du pool frontal VIP.
    
- **Partage d’applications-** Sélectionnez une valeur pour le niveau de charge.
    
- **Collaboration de données-** Sélectionnez une valeur pour le niveau de charge.
    
- **Messagerie instantanée-** Sélectionnez une valeur pour le niveau de charge.
    
- **Conférences vocales-** Sélectionnez une valeur pour le niveau de charge.
    
> [!NOTE]
> Chacun des scénarios a un bouton **Avancé** situé en regard de celui-ci. Boîtes de dialogue avancées contiennent des valeurs spécifiques pour chaque scénario qui modifient le comportement de l’outil de performances et le Stress et activer la personnalisation. > pour chacun des scénarios d’application Web, si le niveau de charge est **personnalisé**, puis la valeur spécifiée dans le ** ConversationsPerHour** champ est utilisé à la place la valeur par défaut.
  
#### <a name="mobility-tab"></a>Onglet mobilité

Utilisez cet onglet pour configurer tous les scénarios relatifs à la mobilité.
  
![Chargez l’onglet Mobilité de l’outil de configuration.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Les options proposées sont les suivantes :
  
- **Paramètres de mobilité général-** Cliquez sur **Paramètres supplémentaires** et que la valeur du champ UcwaTargetServerUrl le directeur Pool IP virtuelle ou VIP pool Front-End.
    
- **Présence et Audio/P2P instantanée messagerie-** Sélectionnez une valeur pour le niveau de charge permettent la simulation de la mobilité.
    
> [!NOTE]
> Chacun des scénarios a un bouton **Avancé** situé en regard de celui-ci. Boîtes de dialogue avancées contiennent des valeurs spécifiques pour chaque scénario qui modifient le comportement de l’outil de performances et le Stress et activer la personnalisation. > pour chacun des scénarios de mobilité, si le niveau de charge est **personnalisé**, puis la valeur spécifiée dans le ** ConversationsPerHour** champ est utilisé à la place la valeur par défaut.
  
#### <a name="summary-tab"></a>Summary tab

L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios.
  
![Chargez l’onglet Résumé de l’outil de configuration.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios. 
  
Il est possible de configurer manuellement des plages de numéros d’utilisateur en cochant la case **Activer de génération de plage utilisateur personnalisés** , puis double-cliquez sur le scénario de la table contenant la plage de l’utilisateur que vous souhaitez personnaliser.
  
Vérifiez **(RunClient.bat) ajouter connexion délai lors du démarrage** afin d’inclure des retards dans les fichiers de traitement par lots généré pour correspondre à la vitesse de connexion. Cela est utile pour empêcher la surcharge du serveur lors de la signature dans un grand nombre d’utilisateurs.
  
Cliquez sur **Générer les fichiers** et sélectionnez le dossier dans lequel vous souhaitez générer la configuration. Une boîte de dialogue s’affiche lorsque les fichiers ont été créés avec succès.
  
![Message « Les fichiers de configuration ont été générés correctement ». Cliquez sur OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Exécutez LyncPerfTool
<a name="BKMK_RunTool"> </a>

Vous aurez besoin créer des utilisateurs, des contacts et des scénarios avant d’exécuter le Skype pour Business Server 2015 Stress et des performances, outil (LyncPerfTool.exe). Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, voir [créer des utilisateurs et Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) et [Configurer le profil utilisateur](using-the-tool.md#BKMK_UserProfile) précédemment dans cet article. Exécution de ces outils est permet également de générer un fichier qui s’exécutera en tant que partie d’un fichier de traitement par lots avec l’outil de Stress et de performances avec les paramètres nécessaires inclus.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Le Skype pour outil Business Server 2015 Stress et des performances en cours d’exécution

L’outil de Configuration de charge (UserProfileGenerator.exe) crée un fichier batch qui vous permet d’exécuter l’outil de Stress and Performance (LyncPerfTool.exe) par l’inscription des compteurs de performances et du chargement du fichier de configuration XML. Le fichier batch s’exécute une seule instance de LyncPerfTool.exe par le fichier de configuration. Pour exécuter le fichier de commandes, procédez comme suit :
  
### <a name="run-the-stress-and-performance-test"></a>Exécutez le test de Stress et de performances

1. Copiez le dossier avec les dossiers et les fichiers à l’intérieur du répertoire qui a LyncPerfTool.exe sur chaque ordinateur client. (Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1.28_13.16.16, copiez ce dossier dans le dossier avec LyncPerfTool.exe qu’il contient. Le faire sur chaque client).
    
2. Accédez au dossier du client et exécuter le script de commandes **RunClient** . Vous pouvez également double-cliquer sur le fichier de commandes dans l’Explorateur Windows et s’exécute tous les fichiers de configuration pour ce client. Vous pouvez également exécuter le script à partir d’un dossier client à l’aide de la syntaxe suivante :
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

Pour exécuter l’outil de Stress et de performances directement, ouvrez une invite de commandes et tapez la commande suivante sur la ligne de commande (et lors de cette opération pour la première fois, veillez à enregistrer les compteurs de performance `regsvr32 /i /n /s LyncPerfToolPerf.dll`, comme indiqué dans la note plus loin dans cette rubrique) :
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Pour afficher les valeurs dans le fichier de configuration de l’outil, vous devez inclure le `/displayfile` paramètre dans la commande précédente, afin qu’il ressemble à ceci :
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

À la *fin* du processus, appuyez sur Ctrl + C.
  
> [!NOTE]
> Avant d’exécuter l’outil de Stress et de performances directement, vous devez enregistrer les compteurs de performance via la commande suivante :`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Chaque instance de l’outil de Stress et de performances que vous démarrez commence immédiatement à l’ouverture de session aux utilisateurs, généralement à un taux d’un utilisateur par seconde. 
  
Le taux maximal d’utilisateur ouverture de session pour le pool est environ 12 par seconde. Cela signifie que vous ne doit pas démarrer plus de 12 instances de LyncPerfTool.exe en même temps pendant que les utilisateurs sont toujours l’ouverture de session. Mille utilisateurs prendra environ 20 minutes entièrement se connecter à une seconde.
  
## <a name="interpreting-the-results"></a>Interprétation des résultats
<a name="BKMK_Interpret"> </a>

Le Skype pour Business Server 2015 Stress et l’outil performances dispose de nombreux compteurs qui peuvent vous aider à comprendre ce que fait le client, et qu’il rencontre les problèmes.
  
### <a name="client-counters"></a>Compteurs de client

Chaque instance de LyncPerfTool.exe en cours d’exécution possède une instance distincte des compteurs. Chaque instance est nommée par son ID de processus. Si les clients sont surchargées autres problèmes peuvent se produire. Pour éviter ces problèmes :
  
- Surveiller l’utilisation du processeur et de mémoire sur les ordinateurs clients. Si le processeur est en permanence supérieure à 90 %, réduire le nombre d’utilisateurs.
    
- Lorsque l’encombrement mémoire est élevée, vous pourriez rencontrer des difficultés si le fichier de la Page commence à manquer d’espace. Vérifiez que la Charge dédiée n’est pas en appuyant sur la limite sur l’ordinateur. Si vous exécutez dans les limites de mémoire prendre en compte l’augmentation de la taille de fichier de la Page ou de la réduction du nombre d’utilisateurs.
    
Voici une liste des compteurs de performance clés :
  
**Informations générales**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Time Spent in Minutes  <br/> |Time spent since the process was started.  <br/> |
|Points de terminaison actifs  <br/> |Nombre de points de terminaison actuellement connectés au serveur.  <br/> |
|Ouvertures de session ayant échoué  <br/> |Nombre total d’échecs de connexion point de terminaison.  <br/> |
|Tentatives d’ouverture de session  <br/> |Nombre total de tentatives de connexion point de terminaison.  <br/> |
|Les points de terminaison déconnectés  <br/> |Nombre total de points de terminaison qui ont été déconnectées.  <br/> |
   
**Informations de présence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|SetPresence Calls  <br/> |Nombre total de présence modifier les tentatives. Pour les différents types de modifications de présence, consultez le compteur de Performance appelle SetPresence (Type de présence).  <br/> |
|Réponses NNN pour SetPresence  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Appels GetPresence  <br/> |Nombre total de tentatives de demande get présence.  <br/> |
|Réponses NNN pour GetPresence  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
   
**Adresse des informations de service de carnet d’adresses**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Total number of full or delta file download requests attempted.  <br/> |
|ABS Full/Delta File Downloads Succeeded  <br/> |Total number of full or delta file download requests attempted.  <br/> |
|Requête Web de carnet d’adresses compteurs relatifs de service  <br/> |Fichier Carnet d’adresses télécharger les compteurs associés.  <br/> |
|Appels de WS ABS tentée  <br/> |Nombre total de demandes de service de requête sur le Web adresse carnet a tenté.  <br/> |
|Appels de WS ABS a réussi.  <br/> |Nombre total de demandes de service adresse carnet Web requête a renvoyé un code de réponse correcte.  <br/> |
|Appels de WS ABS ayant échoué  <br/> |Total number of Address Book Web Query service requests that returned an error response code.  <br/> |
   
> [!NOTE]
> Cette catégorie inclut des compteurs permettant de surveiller les téléchargements de fichiers de carnet d’adresses (ABS) de service et les demandes de requête sur le Web adresse carnet. 
  
**Informations sur la distribution (liste)**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Calls Attempted  <br/> |Total number of distribution list expansion (DLX) web service requests attempted.  <br/> |
|Calls Succeeded  <br/> |Total number of DLX web service requests that returned a successful response code.  <br/> |
|Appels ayant échoué  <br/> |Nombre total de demandes de service web DLX a renvoyé un code d’erreur.  <br/> |
   

  
> [!NOTE]
> Les compteurs de performances ci-dessous numéros d’états pour toutes les voix sur IP (VoIP) les appels, y compris les appels vers le serveur de médiation, A / V Conferencing Server, côté serveur, réponse application de groupe et de Standard automatique de conférence, lorsque ces scénarios sont activés. 
  
**Informations de VoIP Basic**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Calls Active  <br/> |Total number of incoming/outgoing voice calls ongoing currently.  <br/> |
|Appels s’est arrêtés  <br/> |Nombre total d’appels de voix entrantes/sortantes est déjà arrêté.  <br/> |
|Appels refusées  <br/> |Nombre total d’appels de voix est refusé.  <br/> |
|Appels entrants/sortants tentées  <br/> |Nombre total de tentative les appels vocaux entrants/sortants.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de voix entrantes et sortantes établies.  <br/> |
|NNN reçus des appels  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Taux de réussite de la VoIP (%)  <br/> |Total des appels appels/Total établi tentées.  <br/> |
   
**Response Group service informations d’appels**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Calls Active  <br/> |Nombre total d’appels actifs pour l’application de groupe de la réponse.  <br/> |
|Appels tentées  <br/> |Nombre total d’appels tentée.  <br/> |
   
**Informations d’appel (IM) de messagerie instantanée**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Calls Active  <br/> |Total number of ongoing incoming/outgoing instant messaging calls.  <br/> |
|Appels s’est arrêtés  <br/> |Nombre total d’appels de messagerie instantanées entrantes/sortantes est déjà arrêté.  <br/> |
|NNN reçus des appels  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|IM Messages Received/Sent  <br/> |Total number of messages received or sent for all sessions.  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |Total number of incoming/outgoing instant messaging calls attempted.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de messagerie instantanée entrantes et sortantes établies.  <br/> |
   
**Informations d’appel partage d’application**

|**Performance Counter**|**Description**|
|:-----|:-----|
|Calls Active  <br/> |Total number of ongoing incoming/outgoing application sharing calls.  <br/> |
|Calls Terminated  <br/> |Nombre total d’appels de partage déjà d’application entrantes/sortantes s’est arrêté.  <br/> |
|NNN reçus des appels  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Appels entrants/sortants tentées  <br/> |Total number of incoming/outgoing application sharing calls attempted.  <br/> |
|Incoming/Outgoing Calls Established  <br/> |Total number of incoming/outgoing application sharing calls established.  <br/> |
   
**CAA Call Information**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Calls Active  <br/> |Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.  <br/> |
|Calls Terminated  <br/> |Total number of incoming/outgoing PSTN calls already terminated.  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |Total number of incoming/outgoing PSTN calls attempted.  <br/> |
|Incoming/Outgoing Calls Established  <br/> |Total number of incoming/outgoing PSTN calls established.  <br/> |
   
**Conference Information**

|**Performance Counter**|**Description**|
|:-----|:-----|
|Active Instant Messaging Conferences  <br/> |Total number of ongoing instant messaging conferences.  <br/> |
|Active Audio/Video Conferences  <br/> |Total number of ongoing audio/video (A/V) conferences.  <br/> |
|Active Application Sharing Conferences  <br/> |Total number of ongoing application sharing conferences.  <br/> |
|Number of Participants  <br/> |Total number of participants currently connected to conferences.  <br/> |
|Conference Schedule Failure  <br/> |Total number of failures while trying to schedule a conference.  <br/> |
|Join Conference Failure  <br/> |Total number of failures while trying to connect to a conference.  <br/> |
   
**UCWA Client Counters**

|**Performance Counter**|**Description**|
|:-----|:-----|
|Total Number of IMMCU Joins Succeeded  <br/> |Total number of instant messaging conferences joined.  <br/> |
|Total Number of DMCU Joins Succeeded  <br/> |Total number of A/V conferences joined.  <br/> |
   

