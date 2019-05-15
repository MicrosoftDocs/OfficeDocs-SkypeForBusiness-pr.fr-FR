---
title: À l’aide de la Skype pour Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Afin d’exécuter la Skype pour Business Server 2015 Stress and Performance Tool, vous aurez besoin pour être en mesure de gérer les utilisateurs, contacts et les profils utilisateur, configurer l’outil pour l’exécution et puis examinez la sortie ou les résultats produits par l’outil.
ms.openlocfilehash: 750e3a85411e49bf1d9f45cbac0e634daba47d89
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904586"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>À l’aide de la Skype pour Business Server 2015 Stress and Performance Tool
 
Afin d’exécuter la Skype pour Business Server 2015 Stress and Performance Tool, vous aurez besoin pour être en mesure de gérer les utilisateurs, contacts et les profils utilisateur, configurer l’outil pour l’exécution et puis examinez la sortie ou les résultats produits par l’outil.
  
Il existe quatre zones nécessaires à l’exécution de la Skype pour Business Server 2015 Stress and Performance Tool (le fichier exécutable est LyncPerfTool.exe) :
  
- [Créer des utilisateurs et des Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurer un profil utilisateur](using-the-tool.md#BKMK_UserProfile)
    
- [Exécutez LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interprétation des résultats](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Créer des utilisateurs et des Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

Vous devez utiliser le Skype pour l’outil de mise en service des utilisateurs Business Server 2015 (SB 2015) (UserProvisioningTool.exe) pour créer des utilisateurs et des contacts pour votre contrainte et les tests de performances.
  
Il s’agit d’une liste de termes utiles pouvant vous être utiles lorsque vous lisez les rubriques :
  
- **Unité d’organisation** - unité d’organisation l’AD DS (AD DS) (OU).
    
- **Fédérés / croisée Pool** - les utilisateurs peuvent communiquer avec les utilisateurs d’autres services de messagerie instantanée (IM).
    
- **Listes de distribution** - ou listes de distribution. Il s’agit d’objets dans AD DS qui contiennent une liste d’utilisateurs de domaine Active Directory. Elles sont utilisées pour faciliter les communications entre les groupes de personnes.
    
- **Service informations d’emplacement** : Skype le service Business Server 2015 qui, lorsqu’il est activé et configuré par téléphone, permet la récupération d’un emplacement physique pour les services E911 (Enhanced 911).
    
- **Numéros de téléphone US** - affectés à l’utilisateur en plus de l’URI SIP qui est utilisé pour acheminer les appels entrants et sortants dans inverse nombre recherche aléatoirement des numéros de téléphone.
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des Contacts à l’aide de UserProvisioningTool.exe

> [!NOTE]
> Avant même de commencer, veillez absolument qu'auquel vous êtes connecté en tant que membre du groupe de sécurité Administrateurs du domaine pour exécuter cet outil. Vous devez pour cela, étant donné que vous allez créer des utilisateurs Active Directory. 
  
Vous devez utiliser le Skype pour l’outil de mise en service Business Server utilisateur pour créer des utilisateurs et des contacts pour la simulation de charge.
  
Le **Skype pour l’outil de mise en service Business Server utilisateur** est installé avec le package **Skype pour Business Server Stress and Performance Tool** . N’oubliez pas que le programme d’installation du package (CapacityPlanningTool.msi) a été exécutée sur le serveur frontal ou le serveur Standard Edition que vous souhaitez tester.
  
Vous pouvez démarrer le Skype pour l’outil de mise en service Business Server utilisateur en exécutant le fichier UserProvisioningTool.exe (situé dans % InstalledDirectory%LyncStressAndPerfTool\LyncStress) sur le serveur frontal ou sur le serveur Standard Edition server.
  
> [!IMPORTANT]
> Lorsque vous créez un grand nombre d’utilisateurs (par exemple, 10 000 ou plus), exécutez la UserProvisioningTool.exe. Vous devez effectuer cette opération car l’outil sera création et configuration des utilisateurs *nouveaux* AD.
  
Ouverture de l’outil de mise en service des utilisateurs, cliquez sur Configuration, sélectionnez la Configuration de la charge. 
  
Pour commencer la configuration des utilisateurs et des contacts, chargez le fichier par défaut inclus dans le package, appelé « SampleData.xml ». Il sera préremplir les champs des exemples de données que vous devrez modifier pour la rendre pertinents pour votre déploiement.
  
Si vous avez un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, vous pouvez charger ce fichier à la place. Renseignez les champs dans l’outil de mise en service des utilisateurs, comme décrit dans les sections ci-dessous.
  
### <a name="to-configure-server-options"></a>Pour configurer les options de serveur :

1. Dans le champ **Nom complet du serveur frontal du Pool fin** , tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou le pool frontal où vous souhaitez héberger les utilisateurs.
    
2. Dans le champ **Préfixe de nom d’utilisateur** , tapez un préfixe que vous souhaitez utiliser pour bust les noms d’utilisateur pour des tests (par exemple, « TestUser »).
    
3. Dans le champ **mot de passe** , tapez un mot de passe qui sera utilisé sur tous les comptes d’utilisateurs de test.
    
4. Dans le champ **Compte de domaine** , tapez le nom de domaine de votre domaine AD actif (celui dans lequel vous souhaitez créer des utilisateurs de test).
    
5. Dans le champ **Unité d’organisation** , tapez le nom du domaine Active Directory où vous souhaitez créer ces utilisateurs de test. (Si l’unité d’organisation n’existe pas déjà, il vous être créée pour vous).
    
6. Dans le champ **indicatif régional** , tapez l’indicatif régional à trois chiffres à être utilisé sur tous les comptes d’utilisateur de test. Assurez-vous que l’indicatif régional que vous avez choisi n’entre en conflit avec les codes de zone des autres utilisateurs dans Active Directory.
    
7. Activez la case à cocher **Activé vocale** , si vous souhaitez activer les utilisateurs de test pour Enterprise Voice.
    
8. Dans le champ **Nombre d’utilisateurs** , donnez le nombre total d’utilisateurs de test que vous souhaitez créer.
    
9. Dans le champ **Index démarrer** , fournir le numéro de départ qui vous servir comme suffixe pour le préfixe de nom d’utilisateur (par exemple, le préfixe est « TestUser », et le premier nom se termine par « 0 » dans l’exemple ci-dessous.)
    
     ![Outil d’affectation d’utilisateurs affichant l’onglet Création d’utilisateur.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Créer le bouton utilisateurs

Lorsque vous cliquez sur le bouton **Créer des utilisateurs** , les paramètres d’entrée que vous avez entré sont validés. S’il existe des erreurs de validation, vous devrez les résoudre. Ou, si toutes les valeurs sont correctes, les utilisateurs démarrera figurant dans Active Directory (dans l’unité d’organisation que vous avez spécifié). Vous verrez une barre de progression au bas de l’outil en cours d’exécution. Ne fermez pas l’application pendant que la barre de progression est active.
  
Création de l’utilisateur prend du temps, veuillez plan en conséquence. Ce processus peut prendre de quelques minutes pour certains utilisateurs, à quelques heures pour un grand nombre d’utilisateurs.
  
Si vous n’avez pas accès au contrôleur de domaine Active Directory dans votre environnement de test, vous pouvez toujours valider la création de l’utilisateur en ouvrant une session en tant qu’un des utilisateurs dans la plage d’utilisateurs que vous avez spécifié pour créer. N’oubliez pas d’utiliser le préfixe et le suffixe, ainsi que la @sipDomain le nom d’utilisateur. Voici un exemple : <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Si les utilisateurs existent déjà, en cliquant sur le bouton Créer des utilisateurs mettra à jour avec les modifications de configuration. 
  
#### <a name="delete-users-button"></a>Supprimer le bouton utilisateurs

Lorsque vous cliquez sur le bouton **Supprimer les utilisateurs** , les paramètres d’entrée de l’onglet seront validées. S’il existe des erreurs de validation, vous serez invité à les résoudre, et si les valeurs d’entrée sont correctes, les utilisateurs de test spécifié seront désactivés et supprimés d’Active Directory. Là encore, une barre de progression s’affiche au bas de cet onglet, et vous ne doivent pas fermer l’application lorsque la barre de progression est active.
  
> [!NOTE]
> Uniquement les numéros de téléphone au format américain sont pris en charge. Numéros de téléphone sont systématiquement affectées aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool.exe sont activés pour Enterprise Voice par défaut. Les scénarios qui utilisent le numéro de téléphone, tels que le standard automatique de conférence ou appels UC-PSTN, utilisent ce numéro de téléphone pour acheminer les appels correctement. Pour cette raison, *chaque utilisateur* doit avoir un *numéro de téléphone unique* .
  
> [!NOTE]
> **Si vous devez créer des utilisateurs à deux reprises, la commande échouera, sauf si vous utilisez un code de zone différent, ou si les utilisateurs précédentes ont été désactivés à l’aide de l’applet de commande Disable-CsUser.**
  
> [!IMPORTANT]
> Avant de créer des contacts, vous devez tout d’abord effectuer la réplication utilisateur (qui est effectuée à partir de l’onglet utilisateurs). 
  
> [!IMPORTANT]
> Si vous venez de créer vos utilisateurs, vous devez attendre que Skype pour la réplication Business Server est terminée et remplit les comptes d’utilisateur dans la base de données. **Si les utilisateurs n’ont pas fini de réplication, vous verrez une erreur.** Vous saurez que lorsque les utilisateurs ont terminé réplication si le Skype pour le service frontal Business Server 2015 a démarré, ou en exécutant correctement l’applet de commande Get-CsUser sur le dernier utilisateur du nombre total que vous avez spécifié.
  
#### <a name="contacts-creation-tab"></a>Onglet Création de contacts

Cet onglet vous permet de donner des détails des contacts des utilisateurs pour vos tests.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de contenu.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Pour configurer les contacts des utilisateurs, procédez comme suit :

1. Dans le champ **Contacts moyenne par utilisateur** , entrez le nombre moyen de contacts dans des listes de contacts pour chaque utilisateur.
    
2. Activez la case à cocher **fixe** si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous souhaitez faire varier le nombre de contacts créés pour les utilisateurs, désactivez cette case à cocher.
    
3. Dans le champ **Groupes de contacts moyenne par utilisateur** , entrez le nombre de groupes de contacts par utilisateur. Ce numéro doit être inférieure à la **Moyenne de Contacts par utilisateur**.
    
4. Dans le champ **fédérés / croisée Pool Contacts pourcentage** , donnez un nombre compris entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.
    
5. Dans le champ **fédérés / croisée préfixe Pool de l’utilisateur** , attribuez le nom d’utilisateur pour les utilisateurs fédérés qui seront ajoutés à la liste des contacts des utilisateurs locaux.
    
6. Dans le champ **fédérés / Pool utilisateur SIP inter-domaine** , attribuez le nom de domaine SIP des utilisateurs fédérés.
    
7. Dans l’onglet **Création de l’utilisateur** Vérifiez que les informations sont correctes. Vos contacts seront créés à partir des valeurs sous l’onglet Création de l’utilisateur.
    
8. Cliquez sur **Créer des Contacts** pour commencer la création du contact. Ce processus peut prendre plusieurs minutes. Une fois terminée, une boîte de dialogue s’affiche avec le message « opération terminée » apparaît. Vous pouvez valider les contacts qui ont été créés en ouvrant une session en tant qu’utilisateur qui a été créé à partir de l’onglet Création de l’utilisateur.
    
> [!NOTE]
> Une fois que les contacts sont créés, cet outil va redémarrer tous les serveurs frontaux dans le pool cible. Peut prendre plus de temps (jusqu'à 2 heures) pour les serveurs frontaux Démarrer, en fonction du nombre de contacts créé par cette opération. 
  
#### <a name="distribution-list"></a>Liste de distribution

Le Skype pour Business Server 2015 Stress and Performance Tool permet de simuler la fonction d’extension de la liste de Distribution (DL) dans le Skype pour client Business 2015. Vous pouvez ignorer cette étape si vous ne souhaitez pas activer le développement de la liste de distribution dans l’outil de configuration des utilisateurs.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de liste de distribution.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
L’onglet liste de Distribution vous permet de créer des listes de distribution qui utilisent le Stress and Performance Tool pour la fonctionnalité de développement de listes de Distribution. Avant de créer des listes de distribution, Skype pour Business Server 2015 doit être déployé, y compris ayant exécuté ForestPrep. Si ce n’est pas le cas, les attributs DL existe pas dans le schéma Active Directory, afin que l’outil ne sera pas en mesure de créer des listes de distribution.
  
### <a name="to-configure-distribution-lists"></a>Pour configurer les listes de Distribution :

1. Dans le champ **Nombre de listes de Distribution** , fournir le nombre total de listes de distribution à créer (ici est recommandé que vous démarrez avec une valeur double le nombre d’utilisateurs que vous avez.).
    
2. Dans le champ **Préfixe de liste de Distribution** , entrez un préfixe qui doivent de toutes les listes de distribution vous créez, par exemple *testDL* . Cela signifie que, à 100 listes de distribution, les noms de votre liste de distribution ressemblera : testDL0, testDL1, jusqu'à testDL99.
    
3. Dans le champ **Minimale membres d’une liste de distribution** , entrez le nombre minimal d’utilisateurs à placer dans chaque liste de distribution.
    
4. Dans le champ **Nombre maximal de membres dans une liste de distribution** , entrez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.
    
#### <a name="create-distribution-lists-button"></a>Créer des listes de Distribution de bouton

Lorsque vous cliquez sur le bouton Créer des listes de Distribution, l’outil interroge Active Directory pour voir si les listes de distribution mise en correspondance que les numéros et le préfixe existent déjà. L’outil crée les listes de distribution qui n’existent pas déjà. Lorsque vous ajoutez des membres à ces nouveaux les listes de Distribution, il vous choisissez les utilisateurs à partir de la plage spécifiée dans l’onglet Création de l’utilisateur.
  
#### <a name="location-info-service-config-tab"></a>Onglet de configuration du Service informations d’emplacement

Le Skype pour Business Server 2015 Stress and Performance Tool peut également générer des fichiers de configuration factice pour le Service informations d’emplacement. Notez que le Service informations d’emplacement généralement n’avoir réduire considérablement les performances sur les serveurs. 
  
![Outil d’affectation d’utilisateurs affichant l’onglet Configuration du service Informations d’emplacement.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si vous choisissez tester cette fonctionnalité, renseignez les valeurs dans le formulaire, cliquez sur le bouton Générer des fichiers de configuration LIS, qui crée. Fichiers CSV appelés :
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Pour importer ces fichiers dans la base de données LIS utilisent ces applets de commande PowerShell :
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurer un profil utilisateur
<a name="BKMK_UserProfile"> </a>

Une fois que vos utilisateurs sont créés (par le biais de l’outil de création d’utilisateur), vous pouvez configurer les profils utilisateur avec le Skype pour l’outil de Configuration de charge 2015 Business Server (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Le Skype pour l’outil de Configuration de charge 2015 Business Server en cours d’exécution

Démarrez l’outil de Configuration de la charge (UserProfileGenerator.exe) et renseignez les onglets. Cet outil crée un répertoire pour chaque du client que vous aurez besoin pour exécuter des simulations de vos ordinateurs. Chaque répertoire client est fourni avec un script pour démarrer le Skype pour Business Server 2015 Stress and Performance tool (LyncPerfTool.exe). Les sections ci-dessous donnera exemples illustrant comment renseigner les champs de chaque onglet de la Skype pour l’outil de Configuration de charge Business Server 2015.
  
> [!IMPORTANT]
> Les valeurs spécifiques à l’utilisateur de l’outil de Configuration de la charge (UserProfileGenerator.exe) doivent correspondre les valeurs spécifiées dans le Skype pour l’outil de création Business Server 2015 utilisateur (UserProvisioningTool.exe) pour le pool. 
  
#### <a name="common-configuration-tab"></a>Onglet Configuration courantes

L’onglet **Configuration courante** de l’outil de Configuration de charge est indiqué ci-dessous. Renseignez les champs de l’onglet Configuration commune, comme décrit dans les étapes suivantes.
  
![Onglet Affectation d’utilisateurs affichant l’onglet Configuration courante.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Dans le champ **Nombre d’ordinateurs disponibles** , tapez le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter l’outil de Stress and Performance (LyncPerfTool.exe). Il est recommandé que vous disposez d’un ordinateur pour chaque 4500 utilisateurs que vous allez être simulation, mais ce numéro peut varier si vous réduisez le niveau de charge ou utiliser uniquement un sous-ensemble des fonctionnalités disponibles de l’outil (niveaux de chargement sont définis sous l’onglet Général scénarios).
    
2. Dans le champ **préfixe pour les noms d’utilisateur** , entrez un préfixe pour le champ nom d’utilisateur de tous les utilisateurs. Pour vous connecter dans la ressource identificateur URI (Uniform) sera : *UserPrefix [Démarrer Index de l’utilisateur... (Nombre d’utilisateurs-1)] @User domaine* , par exemple, myUser009@Contoso.com.
    
3. Dans le champ **mot de passe pour tous les utilisateurs** , entrez le mot de passe utilisé lors de la création des utilisateurs. Si vous laissez ce champ vide le nom d’utilisateur sera définie comme le mot de passe.
    
4. Dans le champ de **L’Index de début de l’utilisateur** , entrez l’index du premier utilisateur à configurer. Vous pouvez configurer des plages différentes pour différents types ou niveaux de charge, mais vous devez exécuter l’outil de Configuration de la charge (UserProfileGenerator.exe) une fois par la plage que vous souhaitez configurer.
    
5. Dans le champ **Nombre d’utilisateurs** , entrez le nombre total d’utilisateurs que vous allez configurer.
    
6. Dans le champ **Domaine de l’utilisateur** , entrez le domaine utilisé pour l’URI SIP. Cela est utilisé pour construire l’URI SIP de chaque utilisateur pour vous connecter à la Skype pour Business Server 2015 serveur frontal ou Standard Edition server et peut être différent du compte de domaine.
    
7. Dans le champ **Compte de domaine** , entrez la connexion au domaine AD DS.
    
8. Dans le champ **Pourcentage MPOP** (pourcentage plusieurs Point de présence), attribuez une valeur pour le pourcentage d’utilisateurs qui sont connectés à partir de plusieurs ordinateurs ou périphériques, par exemple, 10 pour cent.
    
9. Entrez le nombre maximal de points de terminaison simultanés dans le champ **se connecter par seconde (par Instance)** . Il s’agit de la valeur maximale nombre d’ouvertures de session pour vos utilisateurs, et il est recommandé d’un taux inférieur à / égale à 2 par seconde (< = 2).
    
10. Dans le champ **nom complet du Pool ou Proxy d’accès** , entrez le nom de domaine complet (FQDN) du serveur que vous souhaitez que les clients pour se connecter à. Si les utilisateurs sont connectés en externe, vous devez taper le proxy d’accès. Si les utilisateurs sont des utilisateurs internes, attribuez le nom de domaine complet du serveur Standard Edition ou Pool d’entreprise.
    
11. Dans le champ **Port** , entrez le port que vous souhaitez que les utilisateurs à utiliser pour SIP (ici la valeur par défaut est 5061).
    
12. Pour le champ de **Paramètres de serveur de réseau externe** , attribuez le Proxy d’accès ou nom complet du Pool et, là encore, le **Port**. Ces paramètres sont utilisés uniquement pour la simulation de charge de points de terminaison externe.
    
#### <a name="general-scenarios-tab"></a>Onglet Général scénarios

![Chargez l’outil de configuration affichant l’onglet Scénarios généraux.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Vous pouvez configurer les paramètres et les niveaux de charge pour chacun des scénarios généraux offertes par déterminer ce que vous souhaitez exécuter ou laissez désactivée. Voici les options générales :
  
> [!NOTE]
> Valeurs de niveau de charge pour tous les champs, mais Local Services (IIS) sont **désactivés**, **faible**, **moyen**, **élevé**ou **personnalisé**. Si vous sélectionnez n’importe quel paramètre, mais il est désactivé, les configurations sont générées pour chaque client. Résultats à niveau de la charge maximale pris en charge sur le serveur ; moyenne est 60 % de la charge élevée ; faible est de 30 %. 
  
- **Messagerie instantanée-** Cela inclut d’égal à égal et conférence ; Sélectionnez la valeur appropriée pour le niveau de charge.
    
- **Services d’audioconférence-** Choisissez un niveau de charge pour la conférence audio *uniquement* . Appels d’égal à égal seront traités un peu plus tard dans la section **Scénarios de voix** . Ouvrez l’onglet **Options avancées** pour activer MultiView.
    
- **Partage d’application-** Choisissez un niveau de charge pour le partage d’application.
    
- **Collaboration de données-** Choisissez un niveau de charge pour la collaboration de données, qui inclut des conférences de données.
    
- **Développement de listes de distribution :** Cliquez sur le bouton **Avancé** et renseignez le champ avec les mêmes valeurs configurées dans l’onglet liste de distribution de l’outil de création d’utilisateur (UserProvisioningTool.exe). Choisissez un niveau de charge.
    
- **Requête de Web du carnet d’adresses-** Il s’agit du service de recherche de carnet d’adresses plutôt que le téléchargement de fichiers de carnet d’adresses. Si vous souhaitez activer cette option pour les téléchargements de fichiers du carnet d’adresses, cliquez sur le bouton **Avancé** et **EnableABSDownload** la valeur True. Donner une valeur pour le niveau de charge.
    
- **Service Response Group :** Cliquez sur le bouton **Avancé** et spécifiez les URI des groupes de réponse que vous avez déjà créé lorsque vous avez configuré les agents du Service Response Group. Vous devez choisir au moins un groupe de réponse. Pour plus d’informations, utiliser, séparez les groupes Response Group par des points-virgules. Mettre à jour **RGSUriSuffixStartIndex** et **RGSUriSuffixEndIndex** pour les valeurs réelles. Choisissez un niveau de charge.
    
- **Emplacement des informations Services :** Sélectionnez un niveau de charge soit activé ou désactivé.
    
> [!NOTE]
> Chacun des scénarios possède un bouton Avancé situé en regard d’et un ensemble de cases à cocher permettant de variantes pour le paramètre par défaut. 
  
- Choix *d’Ad hoc* autorisera l’outil générer la simulation de conférences qui sera créé au sein de l’heure.
    
- Choix de *Grande Conf* signifie qu’un grand scénario conférence sera simulé.
    
-  *Externe* indique à l’outil pour simuler également aux utilisateurs externes.
    
Les boutons et les cases à cocher sont des valeurs supplémentaires spécifiques à chaque scénario et seront modifier le comportement de la Stress and Performance Tool et personnalisation possibles.
  
Pour chaque scénario sous l’onglet Général scénarios (à l’exception des services (IIS) emplacement), si la valeur de niveau de charge est **personnalisé**, puis la conversation taux est calculé à l’aide du champ correspondant dans la boîte de dialogue Paramètres avancés. Le nom de champ peut varier en fonction du scénario, mais la description du champ indique : *Remarque Ce numéro sera utilisé uniquement si l’option personnalisé est sélectionnée dans le menu de liste déroulante* .
  
Les valeurs **haute**, **moyenne**et **faible**, modifient les taux de conversation par modalité inséré dans le modèle d’utilisateur qui est un équilibre entre tous les scénarios. S’il est nécessaire pour modifier le niveau de charge par modalité en raison d’une différence d’utilisation prévue, utilisez un taux de conversation personnalisé.
  
#### <a name="voice-scenarios-tab"></a>Onglet de scénarios de voix

Il s’agit de l’onglet pour la configuration de tous les scénarios liés à la voix.
  
![Chargez l’onglet Scénarios vocaux de l’outil de configuration.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Vos options sont les suivants :
  
- **VoIP :** Cliquez sur le bouton **Avancé** et ajoutez les valeurs des champs PhoneAreaCode et LocationProfile (plan de numérotation). Vous trouverez également une valeur pour le niveau de charge. Si vous choisissez un niveau de charge pour VoIP ou la passerelle de communications unifiées/RTC activé, puis un réseau téléphonique public commuté (PSTN) pour les communications unifiées (UC) fichier de configuration sera généré pour simuler les appels externes.
    
- **Passerelle de communications unifiées/RTC-** Vous devez choisir une valeur au niveau de la charge, et lorsque vous choisissez tout autre que désactivé, vous avez également fournir une valeur pour le code de zone PSTN en cliquant sur le bouton **Avancé** . Cliquez sur **Ajouter** sous le serveur de médiation et PSTN. Vérifiez que vous disposez d’un itinéraire configuré pour l’indicatif régional.
    
    > [!TIP]
    > Vous pouvez utiliser soit le Skype pour Business le panneau de configuration ou Skype pour Business Management Shell pour vérifier votre configuration d’itinéraire de communications vocales. 
  
- **Intendant Conférence :** Fournir une valeur pour le niveau de charge. Une valeur autre que désactivé activera le champ **Numéro de téléphone** . Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser. Cliquez sur **Options avancées** et attribuez une valeur pour le champ **LocationProfile** .
    
- **Appelez le Service de stationnement-** Dans ce cas, fournissez un niveau de charge.
    
- **Serveur de médiation et RTC-** Chaque serveur de médiation que vous souhaitez utiliser doit son propre simulator PSTN. Une fois que vous avez déterminé le client que vous allez utiliser pour le simulateur, configuration de votre serveur de médiation pour acheminer à l’ordinateur sur le simulateur PSTN vous appelle configuré. Cliquez sur le bouton **Ajouter** pour configurer une valeur pour le serveur de médiation.
    
    > [!NOTE]
    > Chaque scénario a un bouton Avancé situé en regard de son. Boîtes de dialogue avancées contiennent des paramètres spécifiques pour chaque scénario qui permettent la personnalisation et de modifient le comportement de la Stress and Performance Tool. > pour chaque scénario sous l’onglet voix scénarios, si la valeur du niveau de la charge est **personnalisé**, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue Paramètres avancés. Le nom de champ peut varier en fonction du scénario, mais la description du champ indique : *Remarque Ce numéro sera utilisé uniquement si l’option personnalisé est sélectionnée dans le menu de liste déroulante* .
  
#### <a name="web-app-tab"></a>Onglet de l’application Web

![Chargez l’onglet Application web de l’outil de configuration.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web application prend en charge les scénarios de conférence via le serveur Unified Communications Web API (UCWA) qui est installé sur un serveur frontal. Utilisez l’onglet application Web pour configurer tous les scénarios de basés sur l’application web. Les options sont les suivants :
  
- **Paramètres généraux Web App-** Cliquez sur le bouton **Paramètres supplémentaires** et définir le **ReachTargetServerUrl** à la liste Directory adresse IP virtuelle (VIP) de l’adresse IP virtuelle du pool frontal.
    
- **Partage d’application-** Sélectionnez une valeur pour le niveau de charge.
    
- **Collaboration de données-** Sélectionnez une valeur pour le niveau de charge.
    
- **Messagerie instantanée-** Sélectionnez une valeur pour le niveau de charge.
    
- **Conférence vocale-** Sélectionnez une valeur pour le niveau de charge.
    
> [!NOTE]
> Chacun des scénarios possède un bouton **d’Options avancées** situé en regard de son. Boîtes de dialogue avancées contiennent des valeurs spécifiques à chaque scénario qui modifient le comportement de la Stress and Performance Tool et activer customization.> pour chacun des scénarios d’application Web, si le niveau de charge est **personnalisé**, puis la valeur spécifiée dans le ** ConversationsPerHour** champ est utilisé à la place la valeur par défaut.
  
#### <a name="mobility-tab"></a>Onglet de mobilité

Utilisez cet onglet pour configurer tous les scénarios de mobilité.
  
![Chargez l’onglet Mobilité de l’outil de configuration.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Les options sont les suivants :
  
- **Paramètres de mobilité général :** Cliquez sur **Paramètres supplémentaires** , définissez le champ UcwaTargetServerUrl sur le Pool directeur adresse IP virtuelle (VIP) ou l’adresse IP virtuelle du pool frontal.
    
- **Présence et Audio/P2P instantanée messagerie-** Sélectionnez une valeur pour le niveau de charge activer la simulation de mobilité.
    
> [!NOTE]
> Chacun des scénarios possède un bouton **d’Options avancées** situé en regard de son. Boîtes de dialogue avancées contiennent des valeurs spécifiques à chaque scénario qui modifient le comportement de la Stress and Performance Tool et activer customization.> pour chacun des scénarios de mobilité, si le niveau de charge est **personnalisé**, puis la valeur spécifiée dans le ** ConversationsPerHour** champ est utilisé à la place la valeur par défaut.
  
#### <a name="summary-tab"></a>Onglet Résumé

L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios.
  
![Chargez l’onglet Résumé de l’outil de configuration.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios. 
  
Il est possible de configurer manuellement des plages de numéros utilisateur en cochant la case **Activer personnalisé utilisateur plage génération** , puis double-cliquez sur le scénario dans la table contenant la plage de l’utilisateur que vous souhaitez personnaliser.
  
Vérifiez **(RunClient.bat) ajouter connexion délai lors du démarrage** afin d’inclure des retards dans les fichiers générés par lot pour qu’il corresponde au taux de connexion. Cela est utile pour empêcher la surcharge du serveur lorsque vous vous connectez un grand nombre d’utilisateurs.
  
Cliquez sur **Générer les fichiers** , sélectionnez le dossier où vous souhaitez générer la configuration. Une boîte de dialogue apparaît lorsque vos fichiers ont été créés.
  
![Message « Les fichiers de configuration ont été générés correctement ». Cliquez sur OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Exécutez LyncPerfTool
<a name="BKMK_RunTool"> </a>

Vous devez créer des utilisateurs, des contacts et des scénarios avant d’exécuter la Skype pour Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe). Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, voir [créer des utilisateurs et des Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) et [Configurer un profil utilisateur](using-the-tool.md#BKMK_UserProfile) précédemment dans cet article. Exécution de ces outils générera également un fichier qui s’exécuteront avec l’outil de Stress and Performance dans le cadre d’un fichier de commandes avec les paramètres nécessaires inclus.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Exécute la Skype pour Business Server 2015 Stress and Performance tool

L’outil de Configuration de la charge (UserProfileGenerator.exe) crée un fichier de commandes qui vous permet d’exécuter l’outil de Stress and Performance (LyncPerfTool.exe) en enregistrant les compteurs de performances et de chargement du fichier de configuration XML. Le fichier de commandes s’exécute une seule instance de LyncPerfTool.exe par le fichier de configuration. Pour exécuter le fichier de commandes, procédez comme suit :
  
### <a name="run-the-stress-and-performance-test"></a>Exécutez le test de contrainte et de performances

1. Copiez le dossier avec les dossiers de configuration et les fichiers à l’intérieur du répertoire qui a LyncPerfTool.exe sur chaque ordinateur client. (Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1.28_13.16.16, copiez ce dossier dans le dossier avec LyncPerfTool.exe de celui-ci. Cela sur chaque client.)
    
2. Accédez au dossier du client et exécutez le script de commandes **RunClient** . Vous pouvez double-cliquer sur le fichier de commandes dans l’Explorateur Windows et s’exécute tous les fichiers de configuration pour ce client. Vous pouvez également exécuter le script à partir d’un dossier du client à l’aide de la syntaxe suivante :
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Pour exécuter l’outil de Stress and Performance directement, ouvrez une invite de commandes et tapez la commande suivante à la ligne de commande (et lors de cette opération pour la première fois, veillez à enregistrer les compteurs de performance `regsvr32 /i /n /s LyncPerfToolPerf.dll`, comme indiqué dans la Remarque plus loin dans cette rubrique) :
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Pour afficher les valeurs dans le fichier de configuration de l’outil, vous devez inclure le `/displayfile` paramètre dans la commande précédente, afin qu’elle ressemble à ceci :
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

À la *fin* du processus, appuyez sur Ctrl + C.
  
> [!NOTE]
> Avant d’exécuter l’outil de Stress and Performance directement, vous devez inscrire les compteurs de performance par le biais de la commande suivante :`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Chaque instance de l’outil de Stress and Performance que vous démarrez sera immédiatement la connexion d’utilisateurs, généralement sur un taux d’un utilisateur par seconde. 
  
L’utilisateur pointe connexion le taux pour le pool est environ 12 par seconde. Cela signifie que vous ne doivent pas démarrer plus de 12 instances LyncPerfTool.exe en même temps pendant que les utilisateurs sont toujours la connexion. Les utilisateurs des milliers de personnes prendra environ 20 minutes entièrement vous connecter à une seconde.
  
## <a name="interpreting-the-results"></a>Interprétation des résultats
<a name="BKMK_Interpret"> </a>

Le Skype pour Business Server 2015 Stress and Performance Tool dispose de nombreux compteurs qui peuvent vous aider à comprendre ce que fait le client, et si elle est rencontre des problèmes.
  
### <a name="client-counters"></a>Compteurs de client

Chaque instance de LyncPerfTool.exe en cours d’exécution possède une instance distincte de compteurs. Chaque instance est appelée par son ID de processus. Si les clients sont surchargées autres problèmes peuvent survenir. Pour éviter ces problèmes :
  
- Surveiller l’utilisation du processeur et de la mémoire sur les ordinateurs clients. Si l’UC est régulièrement supérieure à 90 %, réduire le nombre d’utilisateurs.
    
- Lorsque l’encombrement mémoire est élevée, vous pouvez rencontrer les problèmes si le fichier de Page commence à saturé. Vérifiez que la Charge dédiée n’est pas en appuyant sur la limite de l’ordinateur. Si vous exécutez dans les limites de mémoire prendre en compte l’augmentation de la taille de fichier de Page ou de réduire le nombre d’utilisateurs.
    
Voici une liste des compteurs de performance clés :
  
**Informations générales**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Durée en Minutes  <br/> |Le temps passé depuis le démarrage du processus.  <br/> |
|Points de terminaison actifs  <br/> |Nombre de points de terminaison actuellement connecté au serveur.  <br/> |
|Ouvertures de session ayant échoué  <br/> |Nombre total d’échecs de connexion du point de terminaison.  <br/> |
|Tentatives d’ouverture de session  <br/> |Nombre total de tentatives de connexion du point de terminaison.  <br/> |
|Points de terminaison déconnectés  <br/> |Nombre total de points de terminaison qui a été déconnecté.  <br/> |
   
**Informations de présence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels SetPresence  <br/> |Nombre total de présence modifier tentatives. Pour les différents types de modifications de présence, voir le compteur de Performance d’appels SetPresence (Type de présence).  <br/> |
|Réponses NNN pour SetPresence  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Appels GetPresence  <br/> |Nombre total de tentatives de demande get présence.  <br/> |
|Réponses NNN pour GetPresence  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
   
**Informations de service de carnet d’adresses**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Téléchargements de fichiers intégral ABS/Delta a tenté  <br/> |Nombre total de complète ou delta demandes de transfert de fichiers a tenté.  <br/> |
|Les téléchargements de fichiers intégral ABS/Delta a réussi  <br/> |Nombre total de complète ou delta demandes de transfert de fichiers a tenté.  <br/> |
|Requête Web du carnet d’adresses compteurs relatifs de service  <br/> |Fichier de carnet d’adresses télécharger les compteurs sont associés.  <br/> |
|Appels de WS ABS a tenté  <br/> |Nombre total de demandes de service de requête sur le Web téléchargeable adresse a tenté.  <br/> |
|ABS WS appels a réussi  <br/> |Nombre total de demandes de service de requête sur le Web téléchargeable adresse a renvoyé un code de réponse positive.  <br/> |
|ABS WS appels ayant échoué  <br/> |Nombre total de demandes de service de requête sur le Web téléchargeable adresse a renvoyé un code de réponse d’erreur.  <br/> |
   
> [!NOTE]
> Cette catégorie inclut des compteurs permettant de surveiller les téléchargements de fichiers du carnet d’adresses (ABS) de service et des demandes de service de requête sur le Web téléchargeable adresse. 
  
**Informations de distribution (liste)**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels a tenté  <br/> |Nombre total de distribution liste d’extension (DLX) demandes du service web a tenté.  <br/> |
|Appels a réussi  <br/> |Nombre total de demandes de service web DLX a renvoyé un code de réponse positive.  <br/> |
|Appels ayant échoué  <br/> |Nombre total de demandes de service web DLX a renvoyé un code de réponse d’erreur.  <br/> |
   

  
> [!NOTE]
> Les compteurs de performance répertoriées ci-dessous numéros de rapport pour tous les voix sur IP (VoIP) appels, y compris les appels vers le serveur de médiation, A / V Conferencing Server, serveur Edge Server, application Response Group et standard automatique de conférence, lorsque ces scénarios sont activés. 
  
**Informations VoIP Basic**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Les appels actifs  <br/> |Nombre total de voix entrantes et sortantes appelle actuellement en cours.  <br/> |
|Appels terminées  <br/> |Nombre total d’appels de voix entrantes et sortantes déjà arrêté.  <br/> |
|Appels refusées  <br/> |Nombre total d’appels vocaux entrants refusés.  <br/> |
|Appels entrant/sortant a tenté  <br/> |Nombre total de tentative d’appels vocaux entrantes et sortantes.  <br/> |
|Appels entrant/sortant établies  <br/> |Nombre total d’appels vocaux d’entrantes et sortantes établies.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Taux de réussite de VoIP (%)  <br/> |Total des appels établie/Total appels a tenté.  <br/> |
   
**Informations d’appeler le service Response Group**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Les appels actifs  <br/> |Nombre total d’appels actives de l’application Response Group.  <br/> |
|Appels a tenté  <br/> |Nombre total d’appels a tenté.  <br/> |
   
**Informations d’appel (IM) de messagerie instantanée**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Les appels actifs  <br/> |Nombre total d’en cours entrantes et sortantes instantanées appels de messagerie.  <br/> |
|Appels terminées  <br/> |Nombre total d’appels de messagerie instantanées entrantes et sortantes déjà arrêté.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Messages instantanés reçus/envoyés  <br/> |Nombre total de messages envoyés à toutes les sessions ou reçus.  <br/> |
|Appels entrant/sortant a tenté  <br/> |Nombre total d’entrantes et sortantes instantanées appels de messagerie a tenté.  <br/> |
|Appels entrant/sortant établies  <br/> |Nombre total d’appels de messagerie instantanée entrantes et sortantes établies.  <br/> |
   
**Informations d’appel partage d’application**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Les appels actifs  <br/> |Nombre total d’appels de partage d’application en cours entrantes et sortantes.  <br/> |
|Appels terminées  <br/> |Nombre total d’appels de partage déjà d’application entrantes et sortantes interrompue.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn provenant du serveur.  <br/> |
|Appels entrant/sortant a tenté  <br/> |Nombre total d’appels a tenté de partage d’application entrantes et sortantes.  <br/> |
|Appels entrant/sortant établies  <br/> |Nombre total d’appels établies de partage d’application entrantes et sortantes.  <br/> |
   
**Informations sur les appels CAA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Les appels actifs  <br/> |Nombre total d’entrantes et sortantes du réseau téléphonique commuté (RTC) appelle actuellement en cours.  <br/> |
|Appels terminées  <br/> |Nombre total d’appels PSTN entrantes et sortantes déjà arrêté.  <br/> |
|Appels entrant/sortant a tenté  <br/> |Nombre total d’appels PSTN entrantes et sortantes a tenté.  <br/> |
|Appels entrant/sortant établies  <br/> |Nombre total d’appels PSTN entrantes et sortantes établies.  <br/> |
   
**Informations sur la conférence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Conférences par messagerie instantanée actives  <br/> |Nombre total de conférences par messagerie instantanée en cours.  <br/> |
|Conférences Audio/vidéo actives  <br/> |Nombre total en cours audio/vidéo (A / V) conférences.  <br/> |
|Conférences de partage d’Application Active  <br/> |Nombre total de conférences de partage d’application en cours.  <br/> |
|Nombre de Participants  <br/> |Nombre total de participants est actuellement connecté à des conférences.  <br/> |
|Échec de planification de conférence  <br/> |Nombre total d’échecs lors de la tentative planifier une conférence.  <br/> |
|Joindre la conférence Échec  <br/> |Nombre total d’échecs en essayant de se connecter à une conférence.  <br/> |
   
**Compteurs de Client UCWA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Nombre total de IMMCU joint a réussi  <br/> |Nombre total de conférences par messagerie instantanée lié.  <br/> |
|Nombre total de DMCU joint a réussi  <br/> |Nombre total d’A / vidéoconférences lié.  <br/> |
   

