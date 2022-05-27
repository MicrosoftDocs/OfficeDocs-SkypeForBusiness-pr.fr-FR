---
title: Utilisation de l’outil stress et performances Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: Pour exécuter l’outil stress et performances Skype Entreprise Server 2015, vous devez être en mesure de gérer les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil pour l’exécution, puis d’examiner la sortie ou les résultats générés par l’outil.
ms.openlocfilehash: 300da4109ddbdbf06f6dcfbe241cc45c83ec82ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675726"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Utilisation de l’outil stress et performances Skype Entreprise Server 2015
 
Pour exécuter l’outil stress et performances Skype Entreprise Server 2015, vous devez être en mesure de gérer les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil pour l’exécution, puis d’examiner la sortie ou les résultats générés par l’outil.
  
Quatre domaines sont impliqués dans l’exécution de l’outil stress et performances Skype Entreprise Server 2015 (l’exécutable est LyncPerfTool.exe) :
  
- [Créer des utilisateurs et des contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurer le profil utilisateur](using-the-tool.md#BKMK_UserProfile)
    
- [Exécuter LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interprétation des résultats](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Créer des utilisateurs et des contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

Vous devez utiliser l’outil d’approvisionnement d’utilisateurs Skype Entreprise Server 2015 (SB 2015) (UserProvisioningTool.exe) pour créer des utilisateurs et des contacts pour vos tests de contrainte et de performances.
  
Il s’agit d’une liste de termes utiles qui peuvent être utiles lorsque vous lisez les rubriques :
  
- **Unité organisationnelle** : unité d’organisation (UO) services de domaine Active Directory (AD DS).
    
- **Fédéré/pool croisé** : utilisateurs qui peuvent communiquer avec les utilisateurs à partir d’autres services de messagerie instantanée.
    
- **Listes de distribution** - Ou DLL. Il s’agit d’objets dans AD DS qui contiennent une liste d’utilisateurs AD DS. Ils sont utilisés pour faciliter les communications entre les groupes de personnes.
    
- **Service d’informations** sur l’emplacement : service Skype Entreprise Server 2015 qui, lorsqu’il est activé et configuré par téléphone, permet la récupération de l’emplacement physique pour les services 911 améliorés (E911).
    
- **U.S. Téléphone Numbers** - Téléphone nombres attribués à l’utilisateur en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants dans la recherche de numéros inversés (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool.exe

> [!NOTE]
> Avant même de commencer, assurez-vous que vous êtes connecté en tant que membre du groupe de sécurité Administrateurs de domaine pour exécuter cet outil. Vous devez le faire, car vous allez créer des utilisateurs Active Directory. 
  
Vous devez utiliser l’outil d’approvisionnement d’utilisateurs Skype Entreprise Server pour créer des utilisateurs et des contacts pour la simulation de charge.
  
**L’outil d’approvisionnement d’utilisateurs Skype Entreprise Server** est installé avec le package **Outil de contrainte et de performances Skype Entreprise Server**. Assurez-vous que le programme d’installation du package (CapacityPlanningTool.msi) a été exécuté sur le serveur frontal ou le serveur Édition Standard que vous envisagez de tester.
  
Vous pouvez démarrer l’outil Skype Entreprise Server User Provisioning en exécutant le fichier UserProvisioningTool.exe (situé sur %InstalledDirectory%LyncStressAndPerfTool\LyncStress) sur le serveur frontal ou sur le serveur Édition Standard.
  
> [!IMPORTANT]
> Lorsque vous créez un grand nombre d’utilisateurs (par exemple, 10 000 ou plus), exécutez le UserProvisioningTool.exe. Vous devez le faire, car l’outil va créer et configurer de  *nouveaux*  utilisateurs AD.
  
Lorsque l’outil d’approvisionnement d’utilisateurs s’ouvre, cliquez sur Configuration et sélectionnez la configuration de charge. 
  
Pour commencer à configurer les utilisateurs et les contacts, chargez le fichier par défaut inclus dans le package, appelé « SampleData.xml ». Cela préremplira les champs avec des exemples de données que vous devrez modifier pour les rendre pertinents pour votre déploiement.
  
Si vous avez un fichier XML préconfiguré qui contient déjà vos paramètres personnalisés, vous pouvez charger ce fichier à la place. Renseignez les champs de l’outil d’approvisionnement d’utilisateurs, comme décrit dans les sections ci-dessous.
  
### <a name="to-configure-server-options"></a>Pour configurer les options du serveur :

1. Dans le champ **FQDN du pool frontal**, tapez le nom de domaine complet (FQDN) du serveur Édition Standard ou le pool frontal où vous souhaitez héberger les utilisateurs.
    
2. Dans le champ **Préfixe de nom** d’utilisateur, tapez un préfixe que vous souhaitez utiliser pour supprimer vos noms d’utilisateur à des fins de test (par exemple, « TestUser »).
    
3. Dans le champ **Mot de passe, tapez** un mot de passe qui sera utilisé sur tous les comptes d’utilisateur de test.
    
4. Dans le champ **Domaine** de compte, tapez le nom de domaine de votre domaine AD actuel (celui dans lequel vous souhaitez créer vos utilisateurs de test).
    
5. Dans le champ **Unité d’organisation** , tapez le nom du domaine AD dans lequel vous souhaitez créer ces utilisateurs de test. (Si l’unité d’organisation n’existe pas déjà, elle sera créée pour vous).
    
6. Dans le **champ Téléphone Code régional**, tapez le code de zone à trois chiffres à utiliser sur tous les comptes d’utilisateur de test. Assurez-vous que le code régional que vous avez choisi n’entre pas en conflit avec les codes régionaux des autres utilisateurs dans AD.
    
7. Cliquez pour activer la case à cocher **Voix** activée si vous souhaitez activer les utilisateurs de test pour Voix Entreprise.
    
8. Dans le champ **Nombre d’utilisateurs** , indiquez le nombre total d’utilisateurs de test que vous souhaitez créer.
    
9. Dans le champ Index de démarrage, **attribuez** le numéro de départ qui sera utilisé comme suffixe au préfixe de nom d’utilisateur (par exemple, le préfixe est « TestUser » et le prénom se termine par « 0 » dans l’exemple ci-dessous.)
    
     ![Outil d’approvisionnement d’utilisateurs affichant l’onglet Création d’utilisateurs.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Bouton Créer des utilisateurs

Lorsque vous cliquez sur le bouton **Créer des utilisateurs** , les paramètres d’entrée que vous avez entrés sont validés. S’il existe des erreurs de validation, vous êtes invité à les corriger. Ou, si toutes les valeurs sont correctes, les utilisateurs commencent à apparaître dans AD (dans l’unité d’organisation que vous avez spécifiée). Une barre de progression s’affiche en bas de l’outil au fur et à mesure de son exécution. Ne fermez pas l’application tant que la barre de progression est active.
  
La création d’utilisateurs prend du temps. Veuillez donc planifier en conséquence. Ce processus peut prendre plusieurs minutes pour quelques utilisateurs, à quelques heures pour un grand nombre d’utilisateurs.
  
Si vous n’avez pas accès au contrôleur de domaine AD dans votre environnement de test, vous pouvez toujours valider la création d’utilisateurs en vous connectant en tant qu’un des utilisateurs de la plage d’utilisateurs que vous avez spécifiée pour créer. N’oubliez pas d’utiliser le préfixe et le suffixe, ainsi que le @sipDomain comme nom d’utilisateur. Voici un exemple :  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Si les utilisateurs existent déjà, cliquez sur le bouton Créer des utilisateurs pour les mettre à jour avec des modifications de configuration. 
  
#### <a name="delete-users-button"></a>Bouton Supprimer les utilisateurs

Lorsque vous cliquez sur le bouton **Supprimer les utilisateurs** , les paramètres d’entrée de l’onglet sont validés. En cas d’erreurs de validation, vous serez invité à les corriger et, si les valeurs d’entrée sont correctes, les utilisateurs de test spécifiés seront désactivés et supprimés d’Active Directory. Là encore, une barre de progression s’affiche en bas de cet onglet et vous ne devez pas fermer l’application tant que la barre de progression est active.
  
> [!NOTE]
> Seuls les numéros de téléphone au format américain sont pris en charge. Téléphone nombres sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool.exe sont activés pour Voix Entreprise par défaut. Tous les scénarios qui utilisent le numéro de téléphone, comme le standard automatique de conférence ou les appels UC-PSTN, utilisent ce numéro de téléphone pour acheminer correctement les appels. Pour cette raison,  *chaque utilisateur*  doit avoir un *numéro de téléphone unique*  .
  
> [!NOTE]
> **Si vous devez créer des utilisateurs deux fois, la commande échoue, sauf si vous utilisez un autre code régional ou si les utilisateurs précédents ont été désactivés à l’aide de l’applet de commande Disable-CsUser.**
  
> [!IMPORTANT]
> Avant de créer des contacts, vous devez d’abord effectuer la réplication utilisateur (ce qui est fait à partir de l’onglet Utilisateurs). 
  
> [!IMPORTANT]
> Si vous venez de créer vos utilisateurs, vous devez attendre que Skype Entreprise Server réplication se termine et renseigne les comptes d’utilisateur dans la base de données. **Si les utilisateurs n’ont pas terminé la réplication, une erreur s’affiche.** Vous saurez quand les utilisateurs ont terminé la réplication si le service frontal Skype Entreprise Server 2015 a démarré ou en exécutant correctement l’applet de commande Get-CsUser sur le dernier utilisateur du nombre total que vous avez spécifié.
  
#### <a name="contacts-creation-tab"></a>Onglet Création de contacts

Cet onglet vous permet de fournir les détails des contacts des utilisateurs pour vos tests.
  
![Outil d’approvisionnement d’utilisateurs affichant l’onglet Création de contenu.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Pour configurer les contacts des utilisateurs, procédez comme suit :

1. Dans le champ **Contacts moyens par utilisateur** , entrez le nombre moyen de contacts à remplir dans les listes de contacts pour chaque utilisateur.
    
2. Cochez la case **Correction** si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous souhaitez modifier le nombre de contacts créés pour les utilisateurs, désactivez cette case à cocher.
    
3. Dans le champ **Moyenne des groupes de contacts par utilisateur** , entrez le nombre de groupes de contacts par utilisateur. Ce nombre doit être inférieur à la **moyenne des contacts par utilisateur**.
    
4. Dans le champ **Pourcentage de contacts fédérés/entre pools** , attribuez un nombre compris entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.
    
5. Dans le champ **Préfixe d’utilisateur fédéré/entre pools** , attribuez le nom d’utilisateur pour les utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.
    
6. Dans le champ **Domaine SIP de l’utilisateur fédéré/du pool croisé** , attribuez le nom de domaine SIP des utilisateurs fédérés.
    
7. Dans **l’onglet Création d’utilisateur** , vérifiez que les informations sont correctes. Vos contacts seront créés à partir de valeurs sous l’onglet Création d’utilisateurs.
    
8. Cliquez sur **Créer des contacts** pour commencer la création du contact. Ce processus peut prendre plusieurs minutes. Une fois l’opération terminée, une boîte de dialogue s’affiche avec le message « Opération terminée avec succès ». Vous pouvez valider les contacts qui ont été créés en vous connectant en tant qu’utilisateur créé à partir de l’onglet Création d’utilisateurs.
    
    > [!NOTE]
    > Une fois les contacts créés, cet outil redémarre tous les serveurs frontaux dans le pool cible. Le démarrage des serveurs frontaux peut prendre plus de temps (jusqu’à 2 heures), selon le nombre de contacts créés par cette opération. 
  
#### <a name="distribution-list"></a>Liste de distribution

L’outil stress et performances Skype Entreprise Server 2015 peut simuler la fonctionnalité d’extension de liste de distribution (DL) dans le client Skype Entreprise 2015. Vous pouvez ignorer cette étape si vous n’avez pas l’intention d’activer l’extension DL dans l’outil User Provisioning.
  
![Outil d’approvisionnement d’utilisateurs affichant l’onglet Création de liste de distribution.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
L’onglet Liste de distribution vous permet de créer des DLL que l’outil Stress and Performance utilisera pour la fonctionnalité d’extension de liste de distribution. Avant de créer des DLL, Skype Entreprise Server 2015 doit être déployé, notamment après avoir exécuté ForestPrep. Si ce n’est pas fait, les attributs DL n’existent pas dans le schéma AD. L’outil ne pourra donc pas créer de DLL.
  
### <a name="to-configure-distribution-lists"></a>Pour configurer des listes de distribution :

1. Dans le champ **Nombre de listes de distribution** , indiquez le nombre total de DLL que vous souhaitez créer (la recommandation ici est que vous commencez par une valeur qui est le double du nombre d’utilisateurs que vous avez.)
    
2. Dans le champ **Préfixe de liste** de distribution, entrez un préfixe que toutes les DLL que vous créez auront, par exemple *testDL*  . Cela signifie qu’à 100 DL, vos noms DL ressembleront à : testDL0, testDL1, jusqu’à testDL99.
    
3. Dans le champ **Membres minimaux d’un Dist. Liste** , entrez le nombre minimal d’utilisateurs à placer dans chaque DL.
    
4. Dans le champ **Maximum Members in a Dist. List** , entrez le nombre maximal d’utilisateurs à ajouter dans chaque DL.
    
#### <a name="create-distribution-lists-button"></a>Bouton Créer des listes de distribution

Lorsque vous cliquez sur le bouton Créer des listes de distribution, l’outil interroge Active Directory pour voir si les listes de distribution correspondant au préfixe et aux nombres existent déjà. L’outil crée des DLL qui n’existent pas déjà. Lors de l’ajout de membres à ces listes de distribution nouvellement créées, il choisit les utilisateurs dans la plage spécifiée sous l’onglet Création d’utilisateurs.
  
#### <a name="location-info-service-config-tab"></a>Onglet Configuration du service d’informations sur l’emplacement

L’outil stress et performances Skype Entreprise Server 2015 peut également générer des fichiers de configuration factices pour le service d’informations sur l’emplacement. Notez que le service Informations sur l’emplacement n’a généralement pas d’impact significatif sur les performances sur les serveurs. 
  
![Outil d’approvisionnement d’utilisateurs affichant l’onglet Configuration du service d’informations sur l’emplacement.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si vous choisissez de tester cette fonctionnalité, renseignez les valeurs du formulaire et cliquez sur le bouton Générer des fichiers de configuration LIS, qui crée .CSV fichiers appelés :
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Pour importer ces fichiers dans la base de données LIS, utilisez les applets de commande PowerShell suivantes :
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurer le profil utilisateur
<a name="BKMK_UserProfile"> </a>

Une fois vos utilisateurs créés (via l’outil de création d’utilisateurs), vous pouvez configurer des profils utilisateur à l’aide de l’outil de configuration de charge Skype Entreprise Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Exécution de l’outil de configuration de charge Skype Entreprise Server 2015

Démarrez l’outil Load Configuration (UserProfileGenerator.exe) et renseignez les onglets. Cet outil crée un répertoire pour chacun des ordinateurs clients dont vous aurez besoin pour exécuter vos simulations. Chaque répertoire client est fourni avec un script pour démarrer l’outil stress et performances Skype Entreprise Server 2015 (LyncPerfTool.exe). Les sections ci-dessous donnent des exemples de remplissage des champs sous chaque onglet de l’outil de configuration de charge Skype Entreprise Server 2015.
  
> [!IMPORTANT]
> Les valeurs spécifiques à l’utilisateur utilisées dans l’outil Load Configuration (UserProfileGenerator.exe) doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs Skype Entreprise Server 2015 (UserProvisioningTool.exe) pour le pool. 
  
#### <a name="common-configuration-tab"></a>Onglet Configuration commune

L’onglet **Configuration commune** de l’outil de configuration de charge est illustré ci-dessous. Renseignez les champs de l’onglet Configuration commune, comme décrit dans les étapes suivantes.
  
![Onglet Provisionnement d’utilisateurs montrant l’onglet Configuration commune.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Dans le champ **Nombre de machines disponibles** , tapez le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter l’outil Stress and Performance (LyncPerfTool.exe). Nous vous recommandons d’avoir un ordinateur pour 4 500 utilisateurs que vous allez simuler, mais ce nombre peut varier si vous réduisez le niveau de charge ou utilisez uniquement un sous-ensemble des fonctionnalités disponibles de l’outil (les niveaux de charge sont définis sous l’onglet Scénarios généraux).
    
2. Dans le champ **Préfixe des noms d’utilisateur** , entrez un préfixe pour le champ nom d’utilisateur de tous les utilisateurs. Pour vous connecter à l’URI (Uniform Resource Identifier) : *UserPrefix[User Start Index... (Nombre d’utilisateurs-1)] domaine @User*  , par exemple, myUser009@Contoso.com.
    
3. Dans le champ **Mot de passe pour tous les utilisateurs** , entrez le mot de passe utilisé lors de la création des utilisateurs. Si vous laissez ce champ vide, le nom d’utilisateur sera défini comme mot de passe.
    
4. Dans le champ **Index de démarrage** de l’utilisateur, entrez l’index du premier utilisateur à configurer. Vous pouvez configurer différentes plages pour différents types ou niveaux de charge, mais vous devez exécuter l’outil Load Configuration (UserProfileGenerator.exe) une fois par plage que vous souhaitez configurer.
    
5. Dans le champ **Nombre d’utilisateurs** , entrez le nombre total d’utilisateurs que vous allez configurer.
    
6. Dans le champ **Domaine utilisateur** , entrez le domaine utilisé pour l’URI SIP. Il est utilisé pour construire l’URI SIP de chaque utilisateur pour se connecter au serveur frontal Skype Entreprise Server 2015 ou au serveur Édition Standard, et peut être différent du domaine de compte.
    
7. Dans le champ **Domaine de compte** , entrez l’ouverture de session du domaine AD DS.
    
8. Dans le champ **Pourcentage MPOP** (pourcentage de points de présence multiples), attribuez une valeur pour le pourcentage d’utilisateurs connectés à partir de plusieurs ordinateurs ou appareils, par exemple 10 pour cent.
    
9. Entrez le nombre maximal de points de terminaison simultanés dans le champ **Connexion par seconde (par instance).** Il s’agit du nombre maximal de connexions pour vos utilisateurs, et la recommandation est un taux inférieur/égal à 2 par seconde (<=2).
    
10. Dans le champ **Proxy d’accès ou Nom** de domaine complet du pool, entrez le nom de domaine complet (FQDN) du serveur auquel vous souhaitez que les clients se connectent. Si les utilisateurs se connectent en externe, vous devez taper le proxy d’accès. Si les utilisateurs sont internes, indiquez le nom de domaine complet de leur pool Enterprise ou de leur serveur Édition Standard.
    
11. Dans le champ **Port** , entrez le port que vous souhaitez que les utilisateurs utilisent pour SIP (la valeur par défaut est 5061).
    
12. Pour le champ **Paramètres serveur de réseau externe**, indiquez le nom de domaine complet du proxy d’accès ou du pool et, là encore, le **port**. Ces paramètres sont utilisés uniquement pour la simulation de charge des points de terminaison externes.
    
#### <a name="general-scenarios-tab"></a>Onglet Scénarios généraux

![Outil de configuration de charge affichant l’onglet Scénarios généraux.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Vous pouvez configurer les niveaux de charge et les paramètres pour chacun des scénarios généraux proposés en déterminant ce que vous souhaitez exécuter ou laisser désactivé. Voici vos options générales :
  
> [!NOTE]
> Les valeurs de niveau de charge pour tous les champs, sauf les services d’informations locaux, sont **Désactivées**, **Faibles**, **Moyennes**, **Élevées** ou **Personnalisées**. Si vous sélectionnez un paramètre, mais désactivé, des configurations sont générées pour chaque client. Des résultats élevés dans la charge maximale prise en charge sur le serveur ; moyenne est de 60 % de la charge élevée ; est de 30 %. 
  
- **Messagerie instantanée -** Cela inclut le peer-to-peer et la conférence; choisissez la valeur appropriée pour le niveau de charge.
    
- **Audioconférence -** Choisissez un niveau de charge pour l’audioconférence *uniquement*. Les appels d’égal à égal seront abordés un peu plus loin dans la section **Scénarios vocaux** . Ouvrez l’onglet **Avancé** pour activer MultiView.
    
- **Partage d’applications -** Choisissez un niveau de charge pour le partage d’applications.
    
- **Collaboration de données -** Choisissez un niveau de charge pour la collaboration des données, qui inclut la conférence de données.
    
- **Extension de liste de distribution -** Cliquez sur le bouton **Avancé** et renseignez le champ avec les mêmes valeurs configurées sous l’onglet DL de l’outil de création d’utilisateurs (UserProvisioningTool.exe). Choisissez un niveau de charge.
    
- **Requête web carnet d’adresses -** Il s’agit du service de recherche de carnet d’adresses plutôt que du téléchargement du fichier de carnet d’adresses. Si vous souhaitez l’activer pour les téléchargements de fichiers de carnet d’adresses, cliquez sur le bouton **Avancé** et définissez **EnableABSDownload** sur True. Donnez une valeur pour le niveau de charge.
    
- **Service response group -** Cliquez sur le bouton **Avancé** et spécifiez les URI des groupes de réponses que vous avez déjà créés lors de l’approvisionnement des agents Response Group Service. Vous devez choisir au moins un groupe de réponses. Pour en utiliser davantage, séparez les groupes de réponses par des points-virgules. Mettez à jour **RGSUriSuffixStartIndex** et **RGSUriSuffixEndIndex** en fonction des valeurs réelles. Choisissez un niveau de charge.
    
- **Services d’informations sur l’emplacement -** Sélectionnez un niveau de charge activé ou désactivé.
    
> [!NOTE]
> Chacun des scénarios comporte un bouton Avancé situé à côté de celui-ci, ainsi qu’un ensemble de cases à cocher qui activent les variantes du paramètre par défaut. 
  
- Le choix  *d’Ad hoc*  permet à l’outil de générer une simulation de conférences qui seront créées tout au long de l’heure.
    
- Le choix d’une  *grande conf signifie*  qu’un scénario de conférence de grande taille sera simulé.
    
-  *External*  indique à l’outil de simuler également des utilisateurs externes.
    
Ces boutons et cases à cocher sont des valeurs supplémentaires spécifiques à chaque scénario et modifient le comportement de l’outil Stress and Performance et rendent la personnalisation possible.
  
Pour chaque scénario sous l’onglet Scénarios généraux (à l’exception de Location Information Services), si la valeur du niveau de charge est **Personnalisée**, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue Avancé. Le nom du champ peut différer, selon le scénario, mais la description du champ indique :  *REMARQUE Ce nombre sera utilisé uniquement si Custom est sélectionné dans le menu déroulant*  .
  
Les valeurs **High**, **Medium** et **Low** modifient les taux de conversation par modalité conformément au modèle utilisateur qui est un équilibre de tous les scénarios. S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence d’utilisation attendue, utilisez un taux de conversation personnalisé.
  
#### <a name="voice-scenarios-tab"></a>Onglet Scénarios vocaux

Il s’agit de l’onglet pour la configuration de tous vos scénarios relatifs à la voix.
  
![Onglet Scénarios vocaux de l’outil de configuration de charge.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Voici les différents choix possibles :
  
- **VoIP -** Cliquez sur le bouton **Avancé** et ajoutez des valeurs pour les champs PhoneAreaCode et LocationProfile (plan de numérotation). Vous donnerez également une valeur pour le niveau de charge. Si vous choisissez un niveau de charge pour la passerelle VoIP ou UC/PSTN activée, un fichier de configuration de réseau téléphonique commuté (PSTN) public vers un fichier de configuration de communications unifiées (UC) est généré pour simuler des appels externes.
    
- **Passerelle UC/PSTN -** Vous devez choisir une valeur de niveau de charge et, lorsque vous choisissez autre chose que Désactivé, vous devez également fournir une valeur pour le code de zone RTC en cliquant sur le bouton **Avancé** . Cliquez sur **Ajouter** sous le serveur de médiation et le RTC. Assurez-vous qu’un itinéraire est configuré pour le code régional.
    
    > [!TIP]
    > Vous pouvez utiliser le Skype Entreprise Panneau de configuration ou Skype Entreprise Management Shell pour vérifier la configuration de votre itinéraire vocal. 
  
- **Assistant de conférence :** fournissez une valeur pour le niveau de charge. Toute valeur autre que Disabled active le champ **Numéro de téléphone** . Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser. Cliquez sur **Avancé** et attribuez une valeur pour le champ **LocationProfile** .
    
- **Service de stationnement d’appel -** Ici, fournissez un niveau de charge.
    
- **Serveur de médiation et RTC -** Chaque serveur de médiation que vous souhaitez utiliser a besoin de son propre simulateur RTC. Une fois que vous avez déterminé le client que vous allez utiliser pour le simulateur, configurez votre serveur de médiation pour acheminer les appels vers cet ordinateur sur le simulateur RTC que vous avez configuré. Cliquez sur le bouton **Ajouter** pour configurer une valeur pour le serveur de médiation.
    
    > [!NOTE]
    > Chaque scénario comporte un bouton Avancé situé à côté de celui-ci. Les boîtes de dialogue avancées contiennent des paramètres spécifiques à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation. > Pour chaque scénario sous l’onglet Scénarios vocaux, si la valeur du niveau de charge est **Personnalisée**, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue Avancé. Le nom du champ peut différer, selon le scénario, mais la description du champ indique :  *REMARQUE Ce nombre sera utilisé uniquement si Custom est sélectionné dans le menu déroulant*  .
  
#### <a name="web-app-tab"></a>Onglet Application web

![Outil De configuration de charge, onglet Application web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur un serveur frontal. Utilisez l’onglet Application web pour configurer tous les scénarios liés aux applications web. Les options sont :
  
- **Général Web App Paramètres :** cliquez sur le bouton **Paramètres supplémentaire** et définissez **ReachTargetServerUrl** sur l’adresse IP virtuelle du pool d’annuaires de l’adresse IP virtuelle du pool frontal.
    
- **Partage d’applications -** Sélectionnez une valeur pour le niveau de charge.
    
- **Collaboration de données -** Sélectionnez une valeur pour le niveau de charge.
    
- **Messagerie instantanée -** Sélectionnez une valeur pour le niveau de charge.
    
- **Conférence vocale -** Sélectionnez une valeur pour le niveau de charge.
    
> [!NOTE]
> Chacun des scénarios comporte un bouton **Avancé** situé à côté de celui-ci. Les boîtes de dialogue avancées contiennent des valeurs spécifiques à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation.> Pour chacun des scénarios d’application web, si le niveau de charge est **Personnalisé**, la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée au lieu de la valeur par défaut.
  
#### <a name="mobility-tab"></a>Onglet Mobilité

Utilisez cet onglet pour configurer tous les scénarios liés à la mobilité.
  
![Onglet Mobilité de l’outil De configuration de charge.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Voici les options suivantes :
  
- **General Mobility Paramètres :** cliquez sur **Paramètres supplémentaires** et définissez le champ UcwaTargetServerUrl sur l’adresse IP virtuelle du pool d’administrateurs ou l’adresse IP virtuelle du pool frontal.
    
- **Présence et messagerie instantanée/audio P2P -** Sélectionnez une valeur pour le niveau de charge pour activer la simulation mobilité.
    
> [!NOTE]
> Chacun des scénarios comporte un bouton **Avancé** situé à côté de celui-ci. Les dialogues avancés contiennent des valeurs spécifiques à chaque scénario qui modifient le comportement de l’outil Stress and Performance et activent la personnalisation.> Pour chacun des scénarios mobilité, si le niveau de charge est **Personnalisé**, la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée au lieu de la valeur par défaut.
  
#### <a name="summary-tab"></a>Onglet Résumé

L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios.
  
![Onglet Récapitulatif de l’outil De configuration de charge.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
L’onglet Résumé indique les utilisateurs à utiliser pour chacun des scénarios. 
  
Il est possible de configurer manuellement les plages de numéros d’utilisateur en cochant la case **Activer la génération de plages d’utilisateurs personnalisées** , puis en double-cliquant sur le scénario dans le tableau contenant la plage d’utilisateurs que vous souhaitez personnaliser.
  
Vérifiez **(RunClient.bat) Ajouter un délai de connexion au démarrage** afin d’inclure les retards dans les fichiers de lots générés pour correspondre au taux de connexion. Cela est utile pour empêcher la surcharge de serveur lors de la connexion à un grand nombre d’utilisateurs.
  
Cliquez sur **Générer des fichiers** et sélectionnez le dossier dans lequel vous souhaitez générer la configuration. Une boîte de dialogue s’affiche lorsque vos fichiers ont été créés avec succès.
  
![Boîte de message « Charger les fichiers de configuration générés avec succès ». Cliquez simplement sur OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Exécuter LyncPerfTool
<a name="BKMK_RunTool"> </a>

Vous devez créer des utilisateurs, des contacts et des scénarios avant d’exécuter l’outil stress et performances Skype Entreprise Server 2015 (LyncPerfTool.exe). Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, consultez [Créer des utilisateurs et des contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) et [configurer le profil utilisateur](using-the-tool.md#BKMK_UserProfile) précédemment dans cet article. L’exécution de ces outils génère également un fichier qui s’exécutera avec l’outil Stress and Performance dans le cadre d’un fichier de commandes avec les paramètres requis inclus.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Exécution de l’outil stress et performances Skype Entreprise Server 2015

L’outil Load Configuration (UserProfileGenerator.exe) crée un fichier de commandes qui vous permet d’exécuter l’outil Stress and Performance (LyncPerfTool.exe) en inscrivant les compteurs de performances et en chargeant le fichier de configuration XML. Le fichier batch exécute une instance de LyncPerfTool.exe par fichier de configuration. Pour exécuter le fichier batch, procédez comme suit :
  
### <a name="run-the-stress-and-performance-test"></a>Exécuter le test stress et performances

1. Copiez le dossier avec les dossiers de configuration et les fichiers à l’intérieur dans le répertoire qui a LyncPerfTool.exe sur chaque ordinateur client. (Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1.28_13.16.16, copiez ce dossier dans le dossier contenant LyncPerfTool.exe. Effectuez cette opération sur chaque client.)
    
2. Accédez au dossier client et exécutez le script de traitement par lots **RunClient** . Vous pouvez double-cliquer sur le fichier batch dans Windows Explorer et exécuter tous les fichiers de configuration pour ce client. Vous pouvez également exécuter le script à partir d’un dossier client à l’aide de la syntaxe suivante :
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Pour exécuter directement l’outil Stress and Performances, ouvrez une invite de commandes et tapez la commande suivante sur la ligne de commande (et lors de la première opération, veillez à inscrire les compteurs de performances  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, comme indiqué dans la note plus loin dans cette rubrique) :
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Pour que l’outil affiche les valeurs dans le fichier de configuration, incluez le  `/displayfile` paramètre dans la commande précédente, afin qu’il ressemble à ceci :
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Pour  *terminer*  le processus, appuyez sur Ctrl+C.
  
> [!NOTE]
> Avant d’exécuter directement l’outil Stress and Performance, vous devez inscrire les compteurs de performances à l’aide de la commande suivante :  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Chaque instance de l’outil Stress et performances que vous démarrez commence immédiatement à se connecter aux utilisateurs, généralement à un taux d’un utilisateur par seconde. 
  
Le taux maximal de connexion utilisateur pour le pool est d’environ 12 par seconde. Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool.exe en même temps pendant que les utilisateurs se connectent toujours. Un millier d’utilisateurs prend environ 20 minutes pour se connecter entièrement à une par seconde.
  
## <a name="interpreting-the-results"></a>Interprétation des résultats
<a name="BKMK_Interpret"> </a>

L’outil stress et performances Skype Entreprise Server 2015 comporte de nombreux compteurs qui peuvent vous aider à comprendre ce que fait le client et s’il rencontre des problèmes.
  
### <a name="client-counters"></a>Compteurs clients

Chaque instance de LyncPerfTool.exe en cours d’exécution a une instance distincte des compteurs. Chaque instance est nommée par son ID de processus. Si les clients sont surchargés, d’autres problèmes peuvent se produire. Pour éviter ces problèmes :
  
- Surveillez l’utilisation du processeur et de la mémoire sur les ordinateurs clients. Si le processeur est constamment supérieur à 90 %, réduisez le nombre d’utilisateurs.
    
- Lorsque l’encombrement de la mémoire est élevé, vous pouvez rencontrer des problèmes si le fichier de page commence à manquer d’espace. Vérifiez que les frais de validation n’atteignent pas la limite sur l’ordinateur. Si vous rencontrez des limites de mémoire, envisagez d’augmenter la taille du fichier de page ou de réduire le nombre d’utilisateurs.
    
Voici une liste de compteurs de performance clés :
  
**Informations générales**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Temps passé en minutes  <br/> |Temps passé depuis le début du processus.  <br/> |
|Points de terminaison actifs  <br/> |Nombre de points de terminaison actuellement connectés au serveur.  <br/> |
|Échec des journaux d’activité  <br/> |Nombre total d’échecs de connexion de point de terminaison.  <br/> |
|Tentatives d’ouverture de session  <br/> |Nombre total de tentatives de connexion de point de terminaison.  <br/> |
|Points de terminaison déconnectés  <br/> |Nombre total de points de terminaison qui ont été déconnectés.  <br/> |
   
**Informations de présence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|SetPresence Calls  <br/> |Nombre total de tentatives de modification de présence. Pour connaître les différents types de modifications de présence, consultez le compteur de performances d’appels SetPresence (type de présence).  <br/> |
|Réponses NNN pour SetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Appels GetPresence  <br/> |Nombre total de tentatives de demande de présence Get.  <br/> |
|Réponses NNN pour GetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
   
**Informations sur le service Carnet d’adresses**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Tentatives de téléchargements de fichiers ABS complets/delta  <br/> |Nombre total de demandes de téléchargement de fichiers complètes ou delta tentées.  <br/> |
|Téléchargements de fichiers ABS complets/delta réussis  <br/> |Nombre total de demandes de téléchargement de fichiers complètes ou delta tentées.  <br/> |
|Compteurs liés au service de requête web carnet d’adresses  <br/> |Compteurs associés de téléchargement de fichier de carnet d’adresses.  <br/> |
|Appels ABS WS tentés  <br/> |Nombre total de demandes de service de requête web de carnet d’adresses tentées.  <br/> |
|Appels ABS WS réussis  <br/> |Nombre total de demandes de service de requête web carnet d’adresses qui ont renvoyé un code de réponse réussi.  <br/> |
|Échec des appels ABS WS  <br/> |Nombre total de demandes de service de requête web carnet d’adresses qui ont retourné un code de réponse d’erreur.  <br/> |
   
> [!NOTE]
> Cette catégorie inclut les compteurs utilisés pour surveiller les téléchargements de fichiers abs (Address Book Service) et les demandes de service de requête web du carnet d’adresses. 
  
**Informations sur la liste de distribution (DL)**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels tentés  <br/> |Nombre total de demandes de service web DLX (distribution list expansion) tentées.  <br/> |
|Appels réussis  <br/> |Nombre total de demandes de service web DLX qui ont renvoyé un code de réponse réussi.  <br/> |
|Échec des appels  <br/> |Nombre total de demandes de service web DLX qui ont retourné un code de réponse d’erreur.  <br/> |
   

  
> [!NOTE]
> Les compteurs de performances répertoriés ci-dessous indiquent les numéros de tous les appels VoIP (Voice over IP), y compris les appels au serveur de médiation, au serveur de conférence A/V, au serveur Edge, à l’application Response Group et au standard automatique de conférence, lorsque ces scénarios sont activés. 
  
**Informations de base voIP**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels vocaux entrants/sortants en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels vocaux entrants/sortants déjà terminés.  <br/> |
|Appels refusés  <br/> |Nombre total d’appels vocaux entrants refusés.  <br/> |
|Appels entrants/sortants tentés  <br/> |Nombre total d’appels vocaux entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels vocaux entrants/sortants établis.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Taux de réussite VoIP (%)  <br/> |Nombre total d’appels établis/Nombre total d’appels tentés.  <br/> |
   
**Informations d’appel du service Response Group**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels actifs à l’application Response Group.  <br/> |
|Appels tentés  <br/> |Nombre total d’appels tentés.  <br/> |
   
**Informations d’appel de messagerie instantanée**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels entrants/sortants en cours de messagerie instantanée.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels de messagerie instantanée entrants/sortants déjà terminés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Messages instantanés reçus/envoyés  <br/> |Nombre total de messages reçus ou envoyés pour toutes les sessions.  <br/> |
|Appels entrants/sortants tentés  <br/> |Nombre total d’appels de messagerie instantanée entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels instantanés entrants/sortants établis.  <br/> |
   
**Informations d’appel de partage d’application**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de partage d’applications entrants/sortants en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels de partage d’applications entrants/sortants déjà arrêtés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Appels entrants/sortants tentés  <br/> |Nombre total d’appels de partage d’applications entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de partage d’applications entrants/sortants établis.  <br/> |
   
**Informations d’appel caa**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de réseau téléphonique commuté (RTC) entrants/sortants en cours.  <br/> |
|Appels terminés  <br/> |Nombre total d’appels RTC entrants/sortants déjà terminés.  <br/> |
|Appels entrants/sortants tentés  <br/> |Nombre total d’appels RTC entrants/sortants tentés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels RTC entrants/sortants établis.  <br/> |
   
**Informations sur les conférences**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Conférences de messagerie instantanée actives  <br/> |Nombre total de conférences de messagerie instantanée en cours.  <br/> |
|Conférences audio/vidéo actives  <br/> |Nombre total de conférences audio/vidéo (A/V) en cours.  <br/> |
|Conférences de partage d’applications actives  <br/> |Nombre total de conférences de partage d’applications en cours.  <br/> |
|Nombre de participants  <br/> |Nombre total de participants actuellement connectés aux conférences.  <br/> |
|Échec de la planification de conférence  <br/> |Nombre total d’échecs lors de la tentative de planification d’une conférence.  <br/> |
|Échec de la participation à la conférence  <br/> |Nombre total d’échecs lors de la tentative de connexion à une conférence.  <br/> |
   
**Compteurs clients UCWA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Nombre total de jointures IMMCU réussies  <br/> |Nombre total de conférences de messagerie instantanée jointes.  <br/> |
|Nombre total de jointures DMCU réussies  <br/> |Nombre total de conférences A/V jointes.  <br/> |
   

