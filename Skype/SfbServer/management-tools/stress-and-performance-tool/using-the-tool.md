---
title: Utilisation de l Skype Entreprise Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Pour exécuter l’outil stress and performance Skype Entreprise Server 2015, vous devez être en mesure de gérer à la fois les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil pour l’exécuter, puis de passer en revue les résultats produits par l’outil.
ms.openlocfilehash: d54374e81319a6a95ec61fbb2ab5885e2ec368ca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751583"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Utilisation de l Skype Entreprise Server 2015 Stress and Performance Tool
 
Pour exécuter l’outil stress and performance Skype Entreprise Server 2015, vous devez être en mesure de gérer à la fois les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil pour l’exécuter, puis de passer en revue les résultats produits par l’outil.
  
L’exécution de l’outil stress and performance Skype Entreprise Server 2015 implique quatre domaines (l’exécutable est LyncPerfTool.exe) :
  
- [Créer des utilisateurs et des contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurer le profil utilisateur](using-the-tool.md#BKMK_UserProfile)
    
- [Exécuter LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interprétation des résultats](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Créer des utilisateurs et des contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

Vous devez utiliser l’outil Skype Entreprise Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) pour créer des utilisateurs et des contacts pour vos tests de contrainte et de performances.
  
Voici une liste de termes utiles qui peuvent être utiles lorsque vous lisez les rubriques :
  
- **Unité d’organisation** : unité d’organisation des services de domaine Active Directory (AD DS).
    
- **Fédéré/pool croisé** : utilisateurs qui peuvent communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée.
    
- **Listes de distribution** : ou DLs. Il s’agit d’objets dans AD DS qui contiennent une liste d’utilisateurs AD DS. Ils sont utilisés pour faciliter les communications entre les groupes de personnes.
    
- **Service** d’informations d’emplacement : service Skype Entreprise Server 2015 qui, lorsqu’il est activé et configuré par téléphone, permet la récupération de l’emplacement physique pour les services Enhanced 911 (E911).
    
- Numéros de **Téléphone** aux États-Unis : numéros de Téléphone affectés à l’utilisateur en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants dans la recherche de numéros inverses ( RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des contacts à l’aide UserProvisioningTool.exe

> [!NOTE]
> Avant même de commencer, assurez-vous d’être connecté en tant que membre du groupe de sécurité Administrateurs du domaine pour exécuter cet outil. Vous devez le faire, car vous allez créer des utilisateurs Active Directory. 
  
Vous devez utiliser l’outil Skype Entreprise Server de mise en service des utilisateurs pour créer des utilisateurs et des contacts pour la simulation de chargement.
  
**L Skype Entreprise Server approvisionnement** utilisateur est installé avec le package Skype Entreprise Server **Stress and Performance Tool.** Assurez-vous que le programme d’installation du package (CapacityPlanningTool.msi) a été exécuté sur le serveur frontal ou le serveur Édition Standard que vous avez l’intention de tester.
  
Vous pouvez démarrer l’outil de mise en service utilisateur Skype Entreprise Server en exécutant le UserProvisioningTool.exe de fichier (situé dans %InstalledDirectory%LyncStressAndPerfTool\LyncStress) sur le serveur frontal ou sur le serveur Édition Standard.
  
> [!IMPORTANT]
> Lorsque vous créez un grand nombre d’utilisateurs (par exemple, 10 000 ou plus), exécutez le UserProvisioningTool.exe. Vous devrez le faire, car l’outil créera et configurera  *de*  nouveaux utilisateurs AD.
  
Lorsque l’outil d’approvisionnement d’utilisateurs s’ouvre, cliquez sur Configuration et sélectionnez La configuration de chargement. 
  
Pour commencer à configurer les utilisateurs et les contacts, chargez le fichier par défaut inclus dans le package, appelé « SampleData.xml ». Cela pré-insérez des champs avec des exemples de données que vous devrez modifier pour les rendre pertinents pour votre déploiement.
  
Si vous avez un fichier XML préconfiguré qui contient déjà vos paramètres personnalisés, vous pouvez charger ce fichier à la place. Remplissez les champs de l’outil d’approvisionnement d’utilisateurs, comme décrit dans les sections ci-dessous.
  
### <a name="to-configure-server-options"></a>Pour configurer les options du serveur :

1. Dans le champ **FQDN** du pool frontal, tapez le nom de domaine complet (FQDN) du serveur Édition Standard ou le pool frontal dans lequel vous souhaitez héberger les utilisateurs.
    
2. Dans le **champ Préfixe** de nom d’utilisateur, tapez un préfixe que vous souhaitez utiliser pour obtenir vos noms d’utilisateur à des fins de test (par exemple, « TestUser »).
    
3. Dans le **champ Mot** de passe, tapez un mot de passe qui sera utilisé sur tous les comptes d’utilisateur test.
    
4. Dans le **champ Domaine de** compte, tapez le nom de domaine de votre domaine AD actuel (celui dans lequel vous souhaitez créer vos utilisateurs de test).
    
5. Dans le **champ Unité d’organisation,** tapez le nom du domaine AD dans lequel vous souhaitez créer ces utilisateurs de test. (Si l’ou n’existe pas encore, elle sera créée pour vous).
    
6. Dans le **Téléphone code** de zone, tapez le code de zone à trois chiffres à utiliser dans tous les comptes d’utilisateur test. Assurez-vous que le code de zone que vous avez choisi n’entre pas en conflit avec les indicatifs régionaux des autres utilisateurs dans AD.
    
7. Cliquez pour activer la **case à cocher** Voix activée, si vous souhaitez activer les utilisateurs de test pour Voix Entreprise.
    
8. Dans le **champ Nombre d’utilisateurs,** donnez le nombre total d’utilisateurs de test que vous souhaitez créer.
    
9. Dans le champ **Index** de démarrage, indiquez le numéro de départ qui sera utilisé comme suffixe pour le préfixe du nom d’utilisateur (par exemple, le préfixe est « TestUser » et le prénom se termine par « 0 » dans l’exemple ci-dessous.)
    
     ![Outil d’approvisionnement d’utilisateur affichant l’onglet Création d’utilisateur.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Bouton Créer des utilisateurs

Lorsque vous cliquez sur le bouton Créer **des** utilisateurs, les paramètres d’entrée que vous avez entrés sont validés. S’il existe des erreurs de validation, vous serez invité à les corriger. Ou, si toutes les valeurs sont correctes, les utilisateurs commencent à apparaître dans AD (quelle que soit l’ou que vous avez spécifiée). Vous verrez une barre de progression en bas de l’outil lors de son utilisation. Ne fermez pas l’application tant que la barre de progression est active.
  
La création d’utilisateurs prend du temps. Par conséquent, planifiez en conséquence. Ce processus peut prendre entre plusieurs minutes pour quelques utilisateurs et quelques heures pour un grand nombre d’utilisateurs.
  
Si vous n’avez pas accès au contrôleur de domaine AD dans votre environnement de test, vous pouvez toujours valider la création d’utilisateurs en vous connectant en tant qu’un des utilisateurs de la plage d’utilisateurs que vous avez spécifiée pour créer. N’oubliez pas d’utiliser le préfixe et le suffixe, ainsi que le @sipDomain comme nom d’utilisateur. Voici un exemple :  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Si les utilisateurs existent déjà, le fait de cliquer sur le bouton Créer des utilisateurs les met à jour avec les modifications de configuration. 
  
#### <a name="delete-users-button"></a>Bouton Supprimer les utilisateurs

Lorsque vous cliquez sur le bouton **Supprimer les** utilisateurs, les paramètres d’entrée de l’onglet sont validés. S’il existe des erreurs de validation, vous serez invité à les corriger et, si les valeurs d’entrée sont correctes, les utilisateurs de test spécifiés seront désactivés et supprimés d’Active Directory. Là encore, une barre de progression apparaît en bas de cet onglet et vous ne devez pas fermer l’application tant que la barre de progression est active.
  
> [!NOTE]
> Seuls les numéros de téléphone au format américain sont pris en charge. Téléphone numéros sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool.exe sont activés pour Voix Entreprise par défaut. Tous les scénarios qui utilisent le numéro de téléphone, tels que les Standard automatique de conférence ou les appels UC-PSTN, utilisent ce numéro de téléphone pour router correctement les appels. Pour cette raison, *chaque utilisateur* doit avoir un numéro de *téléphone unique.*
  
> [!NOTE]
> **Si vous devez créer deux fois des utilisateurs, la commande échouera, sauf si vous utilisez un autre code de zone ou si les utilisateurs précédents ont été désactivés à l’aide de la cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Avant de créer des contacts, vous devez d’abord effectuer la réplication utilisateur (effectuée à partir de l’onglet Utilisateurs). 
  
> [!IMPORTANT]
> Si vous vient de créer vos utilisateurs, vous devrez attendre la fin de la réplication Skype Entreprise Server et remplir les comptes d’utilisateurs dans la base de données. **Si la réplication des utilisateurs n’est pas terminée, vous verrez une erreur.** Vous savez quand les utilisateurs ont terminé la réplication si le service frontal Skype Entreprise Server 2015 a démarré ou en exécutant correctement la cmdlet Get-CsUser sur le dernier utilisateur du nombre total que vous avez spécifié.
  
#### <a name="contacts-creation-tab"></a>Onglet Création de contacts

Cet onglet vous permet de fournir les détails des contacts des utilisateurs pour vos tests.
  
![Outil d’approvisionnement utilisateur affichant l’onglet Création de contenu.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Pour configurer les contacts des utilisateurs, vous pouvez :

1. Dans le **champ Contacts moyens par** utilisateur, entrez le nombre moyen de contacts à remplir dans les listes de contacts pour chaque utilisateur.
    
2. Cochez **la** case Fixe si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous souhaitez faire varier le nombre de contacts créés pour les utilisateurs, cochez cette case.
    
3. Dans le **champ Groupes de contacts moyens par** utilisateur, entrez le nombre de groupes de contacts par utilisateur. Ce nombre doit être inférieur à la moyenne **des contacts par utilisateur.**
    
4. Dans le **champ Pourcentage de contacts fédérés/entre les pool,** donnez un nombre entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.
    
5. Dans le **champ Préfixe** utilisateur de pool fédéré/croisé, donnez le nom d’utilisateur des utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.
    
6. Dans le champ Domaine SIP de l’utilisateur **fédéré/pool** croisé, donnez le nom de domaine SIP des utilisateurs fédérés.
    
7. Dans **l’onglet Création** d’utilisateurs, assurez-vous que les informations sont correctes. Vos contacts seront créés à partir de valeurs sous l’onglet Création d’utilisateurs.
    
8. Cliquez **sur Créer des contacts** pour commencer la création du contact. Ce processus peut prendre plusieurs minutes. Une fois l’opération terminée, une boîte de dialogue s’affiche avec le message « Opération réussie ». Vous pouvez valider les contacts qui ont été créés en vous connectant en tant qu’utilisateur qui a été créé à partir de l’onglet Création d’utilisateur.
    
    > [!NOTE]
    > Une fois les contacts créés, cet outil redémarre tous les serveurs frontux du pool cible. Le démarrage des serveurs frontux peut prendre plus de temps (jusqu’à 2 heures), selon le nombre de contacts créés par cette opération. 
  
#### <a name="distribution-list"></a>Liste de distribution

L Skype Entreprise Server 2015 Stress and Performance Tool peut simuler la fonctionnalité d’extension de liste de distribution (DL) dans le client Skype Entreprise 2015. Vous pouvez ignorer cette étape si vous n’avez pas l’intention d’activer le développement DL dans l’outil d’approvisionnement des utilisateurs.
  
![Outil d’approvisionnement utilisateur affichant l’onglet Création de liste de distribution.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
L’onglet Liste de distribution vous permet de créer des DL que l’outil Stress and Performance utilisera pour la fonctionnalité d’extension de liste de distribution. Avant de créer des DL, Skype Entreprise Server 2015 doit être déployé, y compris avoir exécuté ForestPrep. Si ce n’est pas fait, les attributs DL n’existent pas dans le schéma AD, donc l’outil ne peut pas créer de DLs.
  
### <a name="to-configure-distribution-lists"></a>Pour configurer des listes de distribution :

1. Dans le champ Nombre de listes de **distribution,** indiquez le nombre total de listes de distribution à créer (il est recommandé de commencer par une valeur qui double le nombre d’utilisateurs dont vous avez besoin).
    
2. Dans le **champ Préfixe de** liste de distribution, entrez un préfixe que toutes les DLs que vous créez auront, par exemple *testDL*  . Cela signifie que, à 100 DL, vos noms DL ressembleront à : testDL0, testDL1, jusqu’à testDL99.
    
3. Dans le **champ Membres minimaux d’un Dist. List,** entrez le nombre minimal d’utilisateurs à placer dans chaque DL.
    
4. Dans le **champ Nombre maximal de membres dans un Dist. List,** entrez le nombre maximal d’utilisateurs à ajouter dans chaque DL.
    
#### <a name="create-distribution-lists-button"></a>Bouton Créer des listes de distribution

Lorsque vous cliquez sur le bouton Créer des listes de distribution, l’outil interroge Active Directory pour voir si les listes de distribution correspondant au préfixe et aux numéros existent déjà. L’outil crée toutes les DLs qui n’existent pas déjà. Lorsque vous ajoutez des membres à ces listes de distribution nouvellement créées, il choisit les utilisateurs dans la plage spécifiée sous l’onglet Création d’utilisateurs.
  
#### <a name="location-info-service-config-tab"></a>Onglet Config du service Informations d’emplacement

L Skype Entreprise Server 2015 Stress and Performance Tool peut également générer des fichiers de configuration factices pour le service Informations d’emplacement. Notez que le service Informations d’emplacement n’a généralement pas d’impact significatif sur les performances sur les serveurs. 
  
![Outil d’approvisionnement utilisateur affichant l’onglet Config du service d’informations d’emplacement.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si vous choisissez de tester cette fonctionnalité, remplissez les valeurs du formulaire, puis cliquez sur le bouton Générer les fichiers de config LIS, qui créera .CSV fichiers appelés :
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Pour importer ces fichiers dans la base de données LIS, utilisez les cmdlets PowerShell ci-après :
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurer le profil utilisateur
<a name="BKMK_UserProfile"> </a>

Une fois vos utilisateurs créés (via l’outil de création d’utilisateurs), vous pouvez configurer les profils utilisateur à l’aide de l’outil Skype Entreprise Server 2015 Load Configuration (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Exécution de l Skype Entreprise Server de configuration load 2015

Démarrez l’outil Charger la configuration (UserProfileGenerator.exe) et remplissez les onglets. Cet outil crée un répertoire pour chacun des ordinateurs clients dont vous aurez besoin pour exécuter vos simulations. Chaque répertoire client est livré avec un script pour démarrer l’outil stress and performance Skype Entreprise Server 2015 (LyncPerfTool.exe). Les sections ci-dessous donnent des exemples de la façon de remplir les champs sous chaque onglet de l’outil Skype Entreprise Server 2015 Load Configuration.
  
> [!IMPORTANT]
> Les valeurs spécifiques à l’utilisateur utilisées dans l’outil De configuration de la charge (UserProfileGenerator.exe) doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs Skype Entreprise Server 2015 (UserProvisioningTool.exe) pour le pool. 
  
#### <a name="common-configuration-tab"></a>Onglet Configuration courante

**L’onglet Configuration commune** de l’outil de configuration de chargement est affiché ci-dessous. Remplissez les champs de l’onglet Configuration commune, comme décrit dans les étapes suivantes.
  
![Onglet Configuration utilisateur affichant l’onglet Configuration commune.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Dans le **champ Nombre d’ordinateurs** disponibles, tapez le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter l’outil Stress and Performance (LyncPerfTool.exe). Nous vous recommandons d’avoir un ordinateur pour 4 500 utilisateurs que vous allez simuler, mais ce nombre peut varier si vous réduisez le niveau de charge ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles de l’outil (les niveaux de charge sont définies sous l’onglet Scénarios généraux).
    
2. Dans le **champ Préfixe des noms d’utilisateurs,** entrez un préfixe pour le champ nom d’utilisateur de tous les utilisateurs. Pour vous connecter à l’URI (Uniform Resource Identifier) sera : *UserPrefix[User Start Index... (Nombre d’utilisateurs -1)] @User, par*  exemple, myUser009@Contoso.com.
    
3. Dans le **champ Mot de passe pour tous les** utilisateurs, entrez le mot de passe utilisé lors de la création des utilisateurs. Si vous laissez ce champ vide, le nom d’utilisateur sera le mot de passe.
    
4. Dans le **champ Index de démarrage de** l’utilisateur, entrez l’index du premier utilisateur à configurer. Vous pouvez configurer différentes plages pour différents types ou niveaux de charge, mais vous devez exécuter l’outil de configuration de charge (UserProfileGenerator.exe) une fois par plage que vous souhaitez configurer.
    
5. Dans le champ Nombre d’utilisateurs, entrez le nombre total d’utilisateurs que vous allez configurer. 
    
6. Dans le **champ Domaine de** l’utilisateur, entrez le domaine utilisé pour l’URI SIP. Il est utilisé pour construire l’URI SIP de chaque utilisateur pour se connecter au serveur frontal Skype Entreprise Server 2015 ou au serveur Édition Standard, et peut être différent du domaine de compte.
    
7. Dans le **champ Domaine du** compte, entrez la logon de domaine AD DS.
    
8. Dans le champ **Pourcentage MPOP** (pourcentage de points de présence multiples), donnez une valeur au pourcentage d’utilisateurs connectés à partir de plusieurs ordinateurs ou appareils, par exemple 10 %.
    
9. Entrez le nombre maximal de points de terminaison simultanés dans le champ **Se connectez par seconde (par instance).** Il s’agit du nombre maximal de connexions pour vos utilisateurs, et la recommandation est un taux inférieur/égal à 2 par seconde (<=2).
    
10. Dans le champ Proxy d’accès ou Nom de domaine complet du **pool,** entrez le nom de domaine complet (FQDN) du serveur à qui vous souhaitez que les clients se connectent. Si les utilisateurs se connectent en externe, vous devez taper le proxy d’accès. Si les utilisateurs sont internes, donnez le nom de Enterprise de leur pool Édition Standard serveur.
    
11. Dans le **champ Port,** entrez le port que vous souhaitez que les utilisateurs utilisent pour SIP (la valeur par défaut est 5061).
    
12. Pour le **champ Serveur réseau Paramètres** externe, donnez au proxy d’accès ou au FQDN du pool et, là encore, le **port**. Ces paramètres sont utilisés uniquement pour la simulation de chargement des points de terminaison externes.
    
#### <a name="general-scenarios-tab"></a>Onglet Scénarios généraux

![Charger l’outil de configuration affichant l’onglet Scénarios généraux.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Vous pouvez configurer les niveaux de charge et les paramètres pour chacun des scénarios généraux proposés en déterminant ce que vous souhaitez exécuter ou laisser désactivé. Voici vos options générales :
  
> [!NOTE]
> Valeurs de niveau de charge pour tous les champs mais les services d’information locaux sont **Désactivés,** **Faible,** **Moyen,** **Élevé** ou **Personnalisé**. Si vous sélectionnez un paramètre, mais désactivé, les configurations sont générées pour chaque client. Résultats élevés de la charge maximale prise en charge sur le serveur ; moyenne est de 60 % de la charge élevée ; faible est de 30 %. 
  
- **Messagerie instantanée :** Cela inclut les conférences d’égal à égal ; choisissez la valeur appropriée pour le niveau de charge.
    
- **Audioconférence -** Choisissez un niveau de charge pour l’audioconférence *uniquement.* Les appels d’égal à égal seront abordés un peu plus loin dans la section **Scénarios de voix.** Ouvrez **l’onglet** Avancé pour activer MultiView.
    
- **Partage d’application :** Choisissez un niveau de charge pour le partage d’application.
    
- **Collaboration de données :** Choisissez un niveau de charge pour la collaboration de données, qui inclut la conférence de données.
    
- **Développement de liste de distribution :** Cliquez sur **le bouton** Avancé et remplissez le champ avec les mêmes valeurs configurées sous l’onglet DL de l’outil de création d’utilisateurs (UserProvisioningTool.exe). Choisissez un niveau de charge.
    
- **Requête web du carnet d’adresses -** Il s’agit du service de recherche de carnet d’adresses plutôt que du téléchargement du fichier de carnet d’adresses. Si vous souhaitez activer cette fonctionnalité pour  les téléchargements de fichiers de carnet d’adresses, cliquez sur le bouton Avancé et définissez **EnableABSDownload** sur True. Donnez une valeur pour le niveau de charge.
    
- **Service Response Group -** Cliquez sur **le bouton** Avancé et spécifiez les URI des groupes Response Groups que vous avez déjà créés lorsque vous avez Service Response Group agents. Vous devez choisir au moins un groupe Response Group. Pour en utiliser plus, séparez les groupes Response Groups par des points-virgules. Mettez **à jour RGSUriSuffixStartIndex** et **RGSUriSuffixEndIndex** sur les valeurs réelles. Choisissez un niveau de charge.
    
- **Services d’informations d’emplacement -** Sélectionnez un niveau de charge activé ou désactivé.
    
> [!NOTE]
> Chacun des scénarios dispose d’un bouton Avancé situé en regard de celui-ci et d’un ensemble de cases à cocher qui activent les variantes au paramètre par défaut. 
  
- Le choix  *ad hoc*  permet à l’outil de générer des simulations de conférences qui seront créées tout au long de l’heure.
    
- Le choix  *d’une*  grande conf signifie qu’un scénario de conférence de grande taille sera simulé.
    
-  *L’externe*  indique à l’outil de simuler également des utilisateurs externes.
    
Ces boutons et cases à cocher sont des valeurs supplémentaires propres à chaque scénario et modifient le comportement de l’outil Stress and Performance et rendent la personnalisation possible.
  
Pour chaque scénario sous l’onglet Scénarios généraux (à l’exception des services d’informations d’emplacement), si la valeur du niveau de charge est **Personnalisée,** la fréquence de conversation sera calculée à l’aide du champ correspondant dans la boîte de dialogue Avancé. Le nom du champ peut varier en fonction du scénario, mais la description du champ sera la suivante : REMARQUE Ce numéro ne sera utilisé que si Custom est sélectionné dans le *menu déroulant.*
  
Les valeurs **Élevée,** **Moyenne** et **Faible,** modifient les taux de conversation par modalité en ligne avec le modèle utilisateur qui est un équilibre de tous les scénarios. S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence d’utilisation attendue, utilisez un taux de conversation personnalisé.
  
#### <a name="voice-scenarios-tab"></a>Onglet Scénarios vocaux

Il s’agit de l’onglet pour la configuration de tous vos scénarios liés à la voix.
  
![Onglet Scénarios vocaux de l’outil De configuration.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Voici les différents choix possibles :
  
- **VoIP -** Cliquez sur **le bouton** Avancé et ajoutez des valeurs pour les champs PhoneAreaCode et LocationProfile (plan de numérotation). Vous devez également fournir une valeur pour le niveau de charge. Si vous choisissez un niveau de charge pour la passerelle VoIP ou UC/PSTN activée, un fichier de configuration de réseau téléphonique commuté (PSTN) vers des communications unifiées (UC) sera généré pour simuler des appels externes.
    
- **Passerelle UC/PSTN -** Vous devez choisir une valeur de niveau de charge, et lorsque vous choisissez autre chose que Désactivé, vous devez également fournir une valeur pour le code de zone PSTN en cliquant sur le bouton **Avancé.** Cliquez **sur Ajouter** sous le serveur de médiation et le réseau PSTN. Assurez-vous qu’un itinéraire est configuré pour le code de zone.
    
    > [!TIP]
    > Vous pouvez utiliser le Panneau de configuration Skype Entreprise ou Skype Entreprise Management Shell pour vérifier la configuration de votre itinéraire de voix. 
  
- **Assistant de conférence -** Fournisse une valeur pour le niveau de charge. Toute valeur autre que Désactivée active le **champ Numéro de** téléphone. Entrez le numéro de téléphone du Standard automatique que vous souhaitez utiliser. Cliquez **sur Avancé** et donnez une valeur au champ **LocationProfile.**
    
- **Service de parc d’appel -** Ici, fournissons un niveau de charge.
    
- **Serveur de médiation et PSTN :** Chaque serveur de médiation que vous souhaitez utiliser a besoin de son propre simulateur PSTN. Une fois que vous avez déterminé le client que vous allez utiliser pour le simulateur, configurez votre serveur de médiation pour router les appels vers cet ordinateur sur le simulateur PSTN que vous avez configuré. Cliquez sur **le bouton** Ajouter pour configurer une valeur pour le serveur de médiation.
    
    > [!NOTE]
    > Chaque scénario possède un bouton Avancé situé à côté de celui-ci. Les boîtes de dialogue avancées contiennent des paramètres spécifiques à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation. > pour chaque scénario de l’onglet Scénarios vocaux, si la valeur du niveau de charge est **Personnalisée,** la fréquence de conversation est calculée à l’aide du champ correspondant dans la boîte de dialogue Avancé. Le nom du champ peut varier en fonction du scénario, mais la description du champ sera la suivante : REMARQUE Ce numéro sera utilisé uniquement si custom est sélectionné dans le *menu déroulant.*
  
#### <a name="web-app-tab"></a>Onglet Application web

![Outil Charger la configuration, onglet Application Web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur un serveur frontal. Utilisez l’onglet Application Web pour configurer tous les scénarios liés à l’application web. Les options sont :
  
- **Général Web App Paramètres -** Cliquez sur **le bouton Paramètres** et définissez **ReachTargetServerUrl** sur l’adresse IP virtuelle (VIP) du pool d’annuaires de l’adresse IP virtuelle du pool frontal.
    
- **Partage d’application :** Sélectionnez une valeur pour le niveau de charge.
    
- **Collaboration de données :** Sélectionnez une valeur pour le niveau de charge.
    
- **Messagerie instantanée :** Sélectionnez une valeur pour le niveau de charge.
    
- **Conférence vocale -** Sélectionnez une valeur pour le niveau de charge.
    
> [!NOTE]
> Chacun des scénarios dispose **d’un bouton Avancé** situé à côté de celui-ci. Les boîtes de dialogue avancées contiennent des valeurs propres à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation.> Pour chacun des scénarios Web App, si le niveau de charge est **Personnalisé,** la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée à la place de la valeur par défaut.
  
#### <a name="mobility-tab"></a>Onglet Mobilité

Cet onglet permet de configurer tous les scénarios liés à la mobilité.
  
![Onglet Mobilité de l’outil de configuration de chargement.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Voici les options disponibles :
  
- **Général Mobility Paramètres -** Cliquez **sur Paramètres** et définissez le champ UcwaTargetServerUrl sur l’adresse IP virtuelle (VIP) du pool directeur ou l’adresse IP virtuelle du pool frontal.
    
- **Présence et messagerie instantanée/audio P2P -** Sélectionnez une valeur pour le niveau de charge pour activer la simulation de mobilité.
    
> [!NOTE]
> Chacun des scénarios dispose **d’un bouton Avancé** situé à côté de celui-ci. Les boîtes de dialogue avancées contiennent des valeurs propres à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation.> Pour chacun des scénarios de mobilité, si le niveau de charge est **Personnalisé,** la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée à la place de la valeur par défaut.
  
#### <a name="summary-tab"></a>Onglet Résumé

L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios.
  
![Onglet Résumé de l’outil De configuration de chargement.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios. 
  
Il est possible de configurer manuellement les plages  de numéro de l’utilisateur en élecliquant sur la case Activer la génération de plage utilisateur personnalisée, puis en double-cliquant sur le scénario dans le tableau qui possède la plage d’utilisateurs que vous souhaitez personnaliser.
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate. Cela est utile pour éviter une surcharge de serveur lors de la signature d’un grand nombre d’utilisateurs.
  
Cliquez **sur Générer des** fichiers et sélectionnez le dossier dans lequel vous souhaitez générer la configuration. Une boîte de dialogue s’affiche lorsque vos fichiers ont été créés avec succès.
  
![Boîte de message « Charger les fichiers de configuration générés avec succès ». Cliquez simplement sur OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Exécuter LyncPerfTool
<a name="BKMK_RunTool"> </a>

Vous devez créer des utilisateurs, des contacts et des scénarios avant d’Skype Entreprise Server 2015 Stress and Performance Tool (LyncPerfTool.exe). Pour plus d’informations sur l’utilisation des outils permettant d’effectuer ces actions, voir [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article. L’exécution de ces outils génère également un fichier qui s’exécutera avec l’outil Stress and Performance dans le cadre d’un fichier de lots avec les paramètres requis inclus.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Exécution de l Skype Entreprise Server 2015 Stress and Performance

L’outil Load Configuration (UserProfileGenerator.exe) crée un fichier de traitement par lots qui vous permet d’exécuter l’outil Stress and Performance (LyncPerfTool.exe) en enregistrant des compteurs de performances et en chargeant le fichier de configuration XML. Le fichier de lots exécute une instance de LyncPerfTool.exe par fichier de configuration. Pour exécuter le fichier de lots, suivez les étapes suivantes :
  
### <a name="run-the-stress-and-performance-test"></a>Exécuter le test Stress and Performance

1. Copiez le dossier avec les dossiers de configuration et les fichiers à l’intérieur du répertoire qui LyncPerfTool.exe sur chaque ordinateur client. (Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1.28_13.16.16, copiez ce dossier dans le dossier LyncPerfTool.exe dans celui-ci. Faites-le sur chaque client.)
    
2. Accédez au dossier client et exécutez le script de lot **RunClient.** Vous pouvez double-cliquer sur le fichier de lots dans Windows Explorer et exécutera tous les fichiers de configuration pour ce client. Vous pouvez également exécuter le script à partir d’un dossier client à l’aide de la syntaxe suivante :
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Pour exécuter l’outil Stress and Performance directement, ouvrez une invite de commandes et tapez la commande suivante sur la ligne de commande (et lorsque vous le faites pour la première fois, assurez-vous d’inscrire les compteurs de performance, comme indiqué dans la remarque plus loin dans cette rubrique) : `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Pour que l’outil affiche les valeurs dans le fichier de configuration, incluez le paramètre sur la commande précédente, afin qu’il  `/displayfile` ressemble à ceci :
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Pour  *terminer*  le processus, appuyez sur Ctrl+C.
  
> [!NOTE]
> Avant d’utiliser directement l’outil Stress and Performance, vous devez inscrire les compteurs de performance via la commande suivante :  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Chaque instance de l’outil Stress and Performance que vous démarrez commence immédiatement à se signer avec les utilisateurs, généralement à un taux d’un utilisateur par seconde. 
  
Le taux de participation maximale de l’utilisateur pour le pool est d’environ 12 par seconde. Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool.exe en même temps pendant que les utilisateurs se sont encore signés. Un millier d’utilisateurs prendra environ 20 minutes pour se connecter entièrement à un utilisateur par seconde.
  
## <a name="interpreting-the-results"></a>Interprétation des résultats
<a name="BKMK_Interpret"> </a>

L Skype Entreprise Server 2015 Stress and Performance Tool dispose de nombreux compteurs qui peuvent vous aider à comprendre ce que fait le client et s’il rencontre des problèmes.
  
### <a name="client-counters"></a>Compteurs clients

Chaque instance de LyncPerfTool.exe en cours d’exécution possède une instance distincte des compteurs. Chaque instance est nommée par son ID de processus. Si les clients sont surchargés, d’autres problèmes peuvent se produire. Pour éviter ces problèmes :
  
- Surveiller l’utilisation du processeur et de la mémoire sur les ordinateurs clients. Si le processeur est constamment supérieur à 90 %, réduisez le nombre d’utilisateurs.
    
- Lorsque l’encombrement mémoire est élevé, vous pouvez être en présence de problèmes si le fichier de page commence à être à court d’espace. Vérifiez que le frais de validation n’atteint pas la limite sur l’ordinateur. Si vous êtes en cours d’exécution dans les limites de mémoire, envisagez d’augmenter la taille du fichier de page ou de réduire le nombre d’utilisateurs.
    
Voici une liste des compteurs de performance clés :
  
**Informations générales**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Temps passé en minutes  <br/> |Temps passé depuis le début du processus.  <br/> |
|Points de terminaison actifs  <br/> |Nombre de points de terminaison actuellement connectés au serveur.  <br/> |
|Échec des connexions  <br/> |Nombre total d’échecs de sign-in de point de terminaison.  <br/> |
|Tentatives d’logo  <br/> |Nombre total de tentatives de connectez-vous au point de terminaison.  <br/> |
|Points de terminaison déconnectés  <br/> |Nombre total de points de terminaison qui ont été déconnectés.  <br/> |
   
**Informations de présence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|SetPresence Calls  <br/> |Nombre total de tentatives de modification de présence. Pour les différents types de modifications de présence, consultez le compteur de performances Appels SetPresence (Type de présence).  <br/> |
|Réponses NNN pour SetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|GetPresence Calls  <br/> |Nombre total de tentatives d’obtenir une demande de présence.  <br/> |
|Réponses NNN pour GetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
   
**Informations sur le service de carnet d’adresses**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Tentatives de téléchargement de fichiers complets/delta du abs  <br/> |Nombre total de demandes de téléchargement de fichiers complètes ou delta tentées.  <br/> |
|Téléchargements complets/delta du fichier ABS réussis  <br/> |Nombre total de demandes de téléchargement de fichiers complètes ou delta tentées.  <br/> |
|Compteurs associés au service de requête web du carnet d’adresses  <br/> |Le fichier de carnet d’adresses télécharge les compteurs associés.  <br/> |
|Tentatives d’appels WS ABS  <br/> |Nombre total de demandes de service de requête web de carnet d’adresses tentées.  <br/> |
|Appels WS ABS réussis  <br/> |Nombre total de demandes de service de requête web de carnet d’adresses qui ont renvoyé un code de réponse réussie.  <br/> |
|Les appels WS ABS ont échoué  <br/> |Nombre total de demandes de service de requête web de carnet d’adresses qui ont renvoyé un code de réponse d’erreur.  <br/> |
   
> [!NOTE]
> Cette catégorie inclut les compteurs utilisés pour surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête web du carnet d’adresses. 
  
**Informations sur les listes de distribution**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels tentés  <br/> |Nombre total de demandes de service web d’extension de liste de distribution (DLX) tentées.  <br/> |
|Appels réussis  <br/> |Nombre total de demandes de service web DLX qui ont renvoyé un code de réponse réussie.  <br/> |
|Appels échoués  <br/> |Nombre total de demandes de service web DLX qui ont renvoyé un code de réponse d’erreur.  <br/> |
   

  
> [!NOTE]
> Les compteurs de performance répertoriés ci-dessous indiquent les numéros de rapport pour tous les appels VoIP (Voice over IP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et les Standard automatique de conférence, lorsque ces scénarios sont activés. 
  
**Informations de base VoIP**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels vocux entrants/sortants en cours actuellement.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels vocux entrants/sortants déjà interrompus.  <br/> |
|Appels refusés  <br/> |Nombre total d’appels vocux entrants refusés.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels vocux entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels vocux entrants/sortants établis.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Taux de réussite VoIP (%)  <br/> |Nombre total d’appels établis/nombre total d’appels tentés.  <br/> |
   
**Informations d’appel du service Response Group**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels actifs à l’application Response Group.  <br/> |
|Appels tentés  <br/> |Nombre total d’appels tentés.  <br/> |
   
**Informations d’appel de messagerie instantanée**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de messagerie instantanée entrants/sortants en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels de messagerie instantanée entrants/sortants déjà terminés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Messages instantanés reçus/envoyés  <br/> |Nombre total de messages reçus ou envoyés pour toutes les sessions.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels de messagerie instantanée entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de messages instantanés entrants/sortants établis.  <br/> |
   
**Informations d’appel de partage d’application**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de partage d’application entrants/sortants en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels de partage d’application entrants/sortants déjà terminés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels de partage d’application entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de partage d’application entrants/sortants établis.  <br/> |
   
**Informations d’appel de l’ACA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels PSTN (réseau téléphonique commuté) entrants/sortants actuellement en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels PSTN entrants/sortants déjà terminés.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels PSTN entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels PSTN entrants/sortants établis.  <br/> |
   
**Informations de conférence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Conférences de messagerie instantanée actives  <br/> |Nombre total de conférences de messagerie instantanée en cours.  <br/> |
|Conférences audio/vidéo actives  <br/> |Nombre total de conférences audio/vidéo (A/V) en cours.  <br/> |
|Conférences actives sur le partage d’application  <br/> |Nombre total de conférences de partage d’application en cours.  <br/> |
|Nombre de participants  <br/> |Nombre total de participants actuellement connectés à des conférences.  <br/> |
|Échec de la planification des conférences  <br/> |Nombre total d’échecs lors de la planification d’une conférence.  <br/> |
|Échec de la conférence de la réunion  <br/> |Nombre total d’échecs lors de la tentative de connexion à une conférence.  <br/> |
   
**Compteurs de clients UCWA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Nombre total de jointeurs IMMCU réussis  <br/> |Nombre total de conférences de messagerie instantanée jointes.  <br/> |
|Nombre total de jointeurs DMCU réussis  <br/> |Nombre total de conférences A/V jointes.  <br/> |
   

