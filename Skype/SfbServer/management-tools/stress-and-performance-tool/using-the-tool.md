---
title: Utilisation de l’outil de stress et de performance 2015 de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Pour exécuter l’outil de stress et de performances de Skype entreprise Server 2015, vous devez être en mesure de gérer les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil d’exécution, puis de passer en revue les résultats produits par l’outil.
ms.openlocfilehash: 0bdffee133e583ebaf4177d3226479838495c69f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888863"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Utilisation de l’outil de stress et de performance 2015 de Skype entreprise Server
 
Pour exécuter l’outil de stress et de performances de Skype entreprise Server 2015, vous devez être en mesure de gérer les utilisateurs, les contacts et les profils utilisateur, de configurer l’outil d’exécution, puis de passer en revue les résultats produits par l’outil.
  
Il existe quatre domaines liés à l’utilisation de l’outil de stress et de performance de Skype entreprise Server 2015 (l’exécutable est LyncPerfTool. exe) :
  
- [Créer des utilisateurs et des contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurer un profil utilisateur](using-the-tool.md#BKMK_UserProfile)
    
- [Exécuter LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interprétation des résultats](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Créer des utilisateurs et des contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

Vous devez utiliser l’outil de mise en service de l’utilisateur Skype entreprise Server 2015 (SB 2015) pour créer des utilisateurs et des contacts pour votre test de stress et de performance.
  
Voici une liste de termes utiles qui peuvent être utiles lorsque vous lisez les rubriques :
  
- **Unité d’organisation** -l’unité d’organisation AD DS (Active Directory Domain Services).
    
- **Regroupement fédéré/croisé** -utilisateurs qui peuvent communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée.
    
- **Listes de distribution** (ou listes de distribution); Il s’agit d’objets dans AD DS qui contiennent une liste d’utilisateurs AD DS. Ils sont utilisés pour faciliter les communications entre les groupes de personnes.
    
- **Service des informations de géolocalisation** : le service Skype entreprise Server 2015 qui, lorsqu’il est activé ou configuré par téléphone, permet la récupération de l’emplacement physique des services E911 (Enhanced enhanced 911).
    
- **Numéros de téléphone U.S.** -numéros de téléphone attribués à l’utilisateur, en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants dans la recherche de numéro inverse (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool. exe

> [!NOTE]
> Avant de commencer, assurez-vous que vous êtes connecté en tant que membre du groupe de sécurité Domain Admins pour exécuter cet outil. Pour cela, vous devez créer des utilisateurs d’Active Directory. 
  
Vous devez utiliser l’outil de mise en service de l’utilisateur Skype entreprise Server pour créer des utilisateurs et des contacts pour la simulation de chargement.
  
L' **outil de mise en service de l’utilisateur Skype entreprise Server** est installé avec le package de l' **outil de stress et de performance de Skype entreprise Server** . Assurez-vous que le programme d’installation de package (CapacityPlanningTool. msi) a été exécuté sur le serveur frontal ou sur le serveur Standard Edition que vous souhaitez tester.
  
Vous pouvez démarrer l’outil de mise en service de l’utilisateur Skype entreprise Server en exécutant le fichier UserProvisioningTool. exe (qui se trouve à% InstalledDirectory% LyncStressAndPerfTool \ LyncStress) sur le serveur frontal ou sur le serveur Standard Edition Server.
  
> [!IMPORTANT]
> Lorsque vous créez un grand nombre d’utilisateurs (par exemple, 10 000 ou plus), exécutez UserProvisioningTool. exe. Vous devez effectuer cette opération, car l’outil crée et configure de *nouveaux* utilisateurs d’annonces.
  
Lorsque l’outil de mise en service de l’utilisateur s’ouvre, cliquez sur Configuration, puis sélectionnez la configuration de chargement. 
  
Pour commencer à configurer les utilisateurs et les contacts, chargez le fichier par défaut inclus dans le package, intitulé « SampleData. Xml ». Cela permet de préremplir les champs avec des exemples de données que vous devez modifier pour le rendre approprié pour votre déploiement.
  
Si vous avez un fichier XML préconfiguré qui contient déjà vos paramètres personnalisés, vous pouvez charger ce fichier à la place. Renseignez les champs dans l’outil de mise en service de l’utilisateur, comme décrit dans les sections ci-dessous.
  
### <a name="to-configure-server-options"></a>Pour configurer les options du serveur :

1. Dans le champ nom de domaine complet (FQDN) du **pool frontal** , tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou du pool frontal dans lequel vous souhaitez héberger les utilisateurs.
    
2. Dans le champ **préfixe nom d’utilisateur** , tapez le préfixe que vous souhaitez utiliser pour encadrer vos noms d’utilisateur à des fins de test (par exemple, « testuser »).
    
3. Dans le champ **mot de passe** , tapez un mot de passe qui sera utilisé dans tous les comptes d’utilisateurs test.
    
4. Dans le champ **Domain Account** , tapez le nom de domaine de votre domaine publicitaire actuel (celui dans lequel vous voulez créer vos utilisateurs de test).
    
5. Dans le champ **unité d’organisation** , entrez le nom du domaine publicitaire dans lequel vous voulez créer ces utilisateurs de test. (Si l’unité d’organisation n’existe pas encore, elle sera créée pour vous).
    
6. Dans le champ **Code de zone téléphonique** , tapez le code de zone à trois chiffres à utiliser dans tous les comptes d’utilisateurs de test. Assurez-vous que l’indicatif de zone que vous avez choisi n’est pas compatible avec les indicatifs des autres utilisateurs dans AD.
    
7. Activez la case à cocher **voix activée** si vous souhaitez activer l’option voix entreprise pour les utilisateurs de test.
    
8. Dans le champ **nombre d’utilisateurs** , entrez le nombre total d’utilisateurs test que vous souhaitez créer.
    
9. Dans le champ **début** , entrez le numéro à utiliser comme suffixe du préfixe du nom d’utilisateur (par exemple, le préfixe « testuser » et le premier nom se termine par « 0 » dans l’exemple ci-dessous).
    
     ![Outil d’affectation d’utilisateurs affichant l’onglet Création d’utilisateur.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Bouton créer des utilisateurs

Lorsque vous cliquez sur le bouton **créer des utilisateurs** , les paramètres d’entrée que vous avez entrés sont validés. S’il existe des erreurs de validation, vous êtes invité à les corriger. Ou bien, si toutes les valeurs sont correctes, les utilisateurs commenceront à apparaître dans AD (quelle que soit l’unité d’organisation que vous avez spécifiée). Une barre de progression apparaît en bas de l’outil lors de son exécution. Ne fermez pas l’application lorsque la barre de progression est active.
  
La création d’utilisateurs prend du temps, alors planifiez en conséquence. Ce processus peut prendre de quelques minutes à quelques minutes pour un grand nombre d’utilisateurs, à quelques heures.
  
Si vous n’avez pas accès au contrôleur de domaine publicitaire dans votre environnement de test, vous pouvez toujours valider la création de l’utilisateur en vous connectant à l’un des utilisateurs de la plage que vous avez spécifiée. N’oubliez pas d’utiliser le préfixe et le suffixe, ainsi que le @sipDomain en tant que nom d’utilisateur. Voici un exemple : <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Si les utilisateurs existent déjà, un clic sur le bouton créer des utilisateurs entraîne la mise à jour avec les modifications apportées à la configuration. 
  
#### <a name="delete-users-button"></a>Bouton supprimer des utilisateurs

Lorsque vous cliquez sur le bouton **supprimer des utilisateurs** , les paramètres d’entrée de l’onglet seront validés. S’il existe des erreurs de validation, vous êtes invité à les résoudre, et si les valeurs d’entrée sont correctes, les utilisateurs de test spécifiés sont désactivés et supprimés d’Active Directory. Là encore, une barre de progression s’affiche au bas de cet onglet, et vous ne devez pas fermer l’application lorsque la barre de progression est active.
  
> [!NOTE]
> Seuls les numéros de téléphone au format U.S. sont pris en charge. Les numéros de téléphone sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool. exe sont activés par défaut pour voix entreprise. Tout scénario utilisant le numéro de téléphone, comme le standard automatique des conférences ou les appels RTC, utilisez ce numéro de téléphone pour acheminer correctement les appels. C’est pourquoi *chaque utilisateur* doit avoir un *numéro de téléphone unique* .
  
> [!NOTE]
> **Si vous devez créer des utilisateurs à deux reprises, la commande échouera, sauf si vous utilisez un indicatif de zone différent ou si les utilisateurs précédents ont été désactivés à l’aide de l’applet de commande Disable-CsUser.**
  
> [!IMPORTANT]
> Avant de créer des contacts, vous devez commencer par procéder à la réplication des utilisateurs (qui est effectuée sous l’onglet utilisateurs). 
  
> [!IMPORTANT]
> Si vous venez de créer vos utilisateurs, vous devez attendre la fin de la réplication de Skype entreprise Server et remplir les comptes des utilisateurs dans la base de données. **Si les utilisateurs n’ont pas terminé la réplication, un message d’erreur s’affiche.** Vous savez alors que les utilisateurs ont fini de procéder à la réplication si le service frontal de Skype entreprise Server 2015 a démarré ou en exécutant correctement la cmdlet Get-CsUser sur le dernier utilisateur du numéro total que vous avez spécifié.
  
#### <a name="contacts-creation-tab"></a>Onglet Création de contacts

Cet onglet vous permet de fournir des informations de contact aux utilisateurs pour vos tests.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de contenu.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Pour configurer les contacts des utilisateurs, procédez comme suit :

1. Dans le champ **moyenne des contacts par utilisateur** , entrez le nombre moyen de contacts à peupler dans les listes de contacts de chaque utilisateur.
    
2. Activez la case à cocher **fixe** si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous voulez modifier le nombre de contacts créés pour les utilisateurs, désactivez cette case à cocher.
    
3. Dans le champ **groupes de contacts moyens par utilisateur** , entrez le nombre de groupes de contacts par utilisateur. Ce numéro doit être inférieur à la **moyenne des contacts par utilisateur**.
    
4. Dans le champ pourcentage des contacts de la **liste des contacts fédérés/du groupe** , entrez un nombre compris entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.
    
5. Dans le champ **préfixe d’utilisateur du pool fédéré/Cross** , attribuez au nom d’utilisateur des utilisateurs fédérés une adresse qui sera ajoutée aux listes de contacts des utilisateurs locaux.
    
6. Dans le champ **Domain SIP de l’utilisateur Federated/Cross pool** , attribuez le nom de domaine SIP aux utilisateurs fédérés.
    
7. Dans l’onglet **création d’utilisateurs** , assurez-vous que les informations sont correctes. Vos contacts seront créés à partir de valeurs sous l’onglet création d’utilisateur.
    
8. Cliquez sur **créer des contacts** pour commencer la création du contact. Ce processus peut prendre quelques minutes. Une fois qu’elle est terminée, une boîte de dialogue s’affiche avec le message « opération terminée correctement ». Vous pouvez valider les contacts créés en vous connectant en tant qu’utilisateur créé à partir de l’onglet création d’utilisateur.
    
    > [!NOTE]
    > Une fois les contacts créés, vous redémarrez tous les serveurs frontaux dans la liste cible. Le début de la période (jusqu’à 2 heures) est susceptible de durer plus longtemps, selon le nombre de contacts créés par cette opération. 
  
#### <a name="distribution-list"></a>Liste de distribution

L’outil de stress et de performance 2015 de Skype entreprise Server peut simuler la fonctionnalité d’extension de liste de distribution (DL) dans le client Skype entreprise 2015. Vous pouvez ignorer cette étape si vous n’avez pas l’intention d’activer l’extension DL dans l’outil de mise en service de l’utilisateur.
  
![Outil d’affectation d’utilisateurs affichant l’onglet Création de liste de distribution.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
L’onglet Liste de distribution vous permet de créer des listes de distribution que l’outil de stress et de performance utilisera pour la fonctionnalité d’extension de liste de distribution. Avant de créer des listes de distribution, Skype entreprise Server 2015 doit être déployé, notamment exécuter ForestPrep. Si ce n’est pas le cas, les attributs DL n’existeront pas dans le schéma publicitaire, de sorte que l’outil ne sera pas en mesure de créer des listes de distribution.
  
### <a name="to-configure-distribution-lists"></a>Pour configurer des listes de distribution :

1. Dans le champ **nombre de listes de distribution** , entrez le nombre total de listes de distribution que vous voulez créer (nous vous conseillons de commencer par une valeur qui correspond au nombre d’utilisateurs que vous avez.).
    
2. Dans le champ **préfixe** de la liste de distribution, entrez le préfixe de toutes les listes de distribution que vous créez, par exemple *testDL* . Ainsi, dans les listes de distribution 100, vos noms de DL se présentent comme suit : testDL0, testDL1, testDL99.
    
3. Dans le champ nombre **minimal de membres d’un champ dist. List** , entrez le nombre d’utilisateurs à inclure dans chaque liste de distribution.
    
4. Dans le champ **nombre maximal de membres d’un champ dist. List** , entrez le nombre maximal d’utilisateurs à ajouter dans chaque LD.
    
#### <a name="create-distribution-lists-button"></a>Bouton créer des listes de distribution

Lorsque vous cliquez sur le bouton créer des listes de distribution, l’outil interroge Active Directory pour voir si les listes de distribution correspondant au préfixe et aux numéros existent déjà. L’outil crée des listes de distribution qui n’existent pas déjà. Lors de l’ajout de membres à ces listes de distribution nouvellement créées, le choix des utilisateurs dans la plage spécifiée dans l’onglet création d’utilisateur.
  
#### <a name="location-info-service-config-tab"></a>Onglet Configuration du service informations de géolocalisation

L’outil de stress et de performance 2015 de Skype entreprise Server peut également générer des fichiers de configuration factices pour le service d’information d’emplacement. Notez que le service des informations d’emplacement n’a généralement pas d’impact notable sur les performances sur les serveurs. 
  
![Outil d’affectation d’utilisateurs affichant l’onglet Configuration du service Informations d’emplacement.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Si vous choisissez de tester cette fonction, entrez les valeurs dans le formulaire et cliquez sur le bouton générer les fichiers de configuration de LIS, qui créera. Fichiers CSV nommés :
  
- LIS_Subnet. csv
    
- LIS_Switches. csv
    
- LIS_Ports. csv
    
- LIS_WAP. csv
    
Pour importer ces fichiers dans la base de données LIS, utilisez les cmdlets PowerShell suivantes :
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurer un profil utilisateur
<a name="BKMK_UserProfile"> </a>

Une fois vos utilisateurs créés (via l’outil de création d’utilisateur), vous pouvez configurer des profils utilisateur avec l’outil de configuration de chargement de Skype entreprise Server 2015 (UserProfileGenerator. exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Exécution de l’outil de configuration de chargement de Skype entreprise Server 2015

Démarrez l’outil de configuration de charge (UserProfileGenerator. exe) et renseignez les onglets. Cet outil crée un répertoire pour chaque ordinateur client sur lequel vous devez exécuter vos simulations. Chaque répertoire client est fourni avec un script pour démarrer l’outil de stress et de performance de Skype entreprise Server 2015 (LyncPerfTool. exe). Les sections ci-dessous donnent des exemples sur la façon de renseigner les champs de chaque onglet de l’outil de configuration de chargement de Skype entreprise Server 2015.
  
> [!IMPORTANT]
> Les valeurs propres à l’utilisateur utilisées dans l’outil de configuration de chargement (UserProfileGenerator. exe) doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateur 2015 de Skype entreprise Server (UserProvisioningTool. exe) pour le pool. 
  
#### <a name="common-configuration-tab"></a>Onglet Configuration commune

L’onglet **configuration commune** de l’outil de configuration de chargement est présenté ci-dessous. Remplissez les champs de l’onglet configuration courante, comme décrit dans les étapes suivantes.
  
![Onglet Affectation d’utilisateurs affichant l’onglet Configuration courante.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Dans le champ **nombre d’ordinateurs disponibles** , tapez le nombre d’ordinateurs que vous voulez utiliser pour exécuter l’outil de stress et de performance (LyncPerfTool. exe). Nous vous recommandons d’avoir un ordinateur pour tous les utilisateurs de 4500 que vous simulez, mais ce nombre peut varier si vous réduisez le niveau de charge, ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles de l’outil (les niveaux de charge sont définis dans l’onglet scénarios généraux).
    
2. Dans le champ **préfixe pour les noms d’utilisateurs** , entrez un préfixe pour le champ nom d’utilisateur de tous les utilisateurs. Pour vous connecter à l’URI (Uniform Resource Identifier), vous devez procéder comme suit : *UserPrefix [index de début de l’utilisateur... (Nombre d’utilisateurs-1)] @User domaine* (par exemple, myUser009@Contoso.com.
    
3. Dans le champ **mot de passe pour tous les utilisateurs** , entrez le mot de passe utilisé lors de la création des utilisateurs. Si vous laissez ce champ vide, le nom d’utilisateur est défini comme mot de passe.
    
4. Dans le champ **index de début** de l’utilisateur, entrez l’index du premier utilisateur à configurer. Vous pouvez configurer différentes plages pour différents types ou niveaux de charge, mais vous devez exécuter l’outil de configuration de charge (UserProfileGenerator. exe) une fois par la plage que vous souhaitez configurer.
    
5. Dans le champ **nombre d’utilisateurs** , entrez le nombre total d’utilisateurs que vous allez configurer.
    
6. Dans le champ **Domain user** , entrez le domaine utilisé pour l’URI SIP. Il est utilisé pour créer l’URI SIP de chaque utilisateur pour se connecter au serveur frontal Skype entreprise Server 2015 ou Standard Edition Server, et peut être différent du domaine du compte.
    
7. Dans le champ **Domain Account** , entrez la connexion au domaine AD DS.
    
8. Dans le champ **pourcentage MPOP** (point de présence multiple du pourcentage de présence), entrez une valeur pour le pourcentage d’utilisateurs connectés à partir de plusieurs machines ou appareils (par exemple, 10 pour cent).
    
9. Entrez le nombre maximal de points de terminaison concurrents dans le champ **connexion par seconde (par instance)** . C’est le nombre maximal de journaux pour vos utilisateurs et la recommandation est un taux inférieur ou égal à 2 par seconde (<= 2).
    
10. Dans le champ **FQDN du proxy d’accès ou du pool** , entrez le nom de domaine complet (FQDN) du serveur auquel vous voulez que les clients se connectent. Si les utilisateurs se connectent en externe, vous devez taper le proxy d’accès. S’il s’agit d’un utilisateur interne, attribuez-lui le nom de domaine complet du pool d’entreprise ou du serveur Standard Edition Server.
    
11. Dans le champ **port** , entrez le port que les utilisateurs utiliseront pour le protocole SIP (la valeur par défaut est 5061).
    
12. Pour le champ **paramètres de serveur de réseau externe** , définissez le nom de domaine complet du proxy ou du pool d’accès et, une fois encore, le **port**. Ces paramètres sont utilisés uniquement pour la simulation de charge de points de terminaison externes.
    
#### <a name="general-scenarios-tab"></a>Onglet scénarios généraux

![Chargez l’outil de configuration affichant l’onglet Scénarios généraux.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Vous pouvez configurer les niveaux de charge et les paramètres pour chacun des scénarios généraux proposés en déterminant ce que vous voulez exécuter ou laisser désactivé. Voici les options qui s’offrent à vous :
  
> [!NOTE]
> Les valeurs de niveau de charge de tous les champs, mais services d’information local sont **désactivées**, **faible**, **moyenne**, **haute**ou **personnalisée**. Si vous sélectionnez un paramètre, mais désactivé, des configurations sont générées pour chaque client. Le résultat est élevé en fonction du chargement maximal pris en charge sur le serveur. le moyen est 60% de charge élevée ; le niveau faible est de 30%. 
  
- **Messagerie instantanée-** Cela inclut les services d’égal à égal et de conférence ; Choisissez la valeur appropriée pour le niveau de charge.
    
- **Audioconférence-** Choisissez un niveau de charge pour les conférences audio *uniquement* . Les appels d’égal à égal seront abordés un peu plus tard dans la section **scénarios vocaux** . Ouvrez l’onglet **avancé** pour activer multivue.
    
- **Partage d’application** Choisissez un niveau de charge pour le partage d’application.
    
- **Collaboration sur les données :** Choisissez un niveau de charge pour la collaboration de données, qui inclut les conférences de données.
    
- **Extension de liste de distribution-** Cliquez sur le bouton **avancé** , puis renseignez le champ avec les mêmes valeurs configurées sous l’onglet DL de l’outil de création d’utilisateurs (UserProvisioningTool. exe). Choisissez un niveau de charge.
    
- **Requête sur le Web du carnet d’adresses** Il s’agit du service de recherche dans le carnet d’adresses plutôt que de télécharger le fichier du carnet d’adresses. Si vous voulez activer cette option pour les téléchargements de fichiers du carnet d’adresses, cliquez sur le bouton **avancé** et définissez **EnableABSDownload** sur true. Attribuez une valeur au niveau de charge.
    
- **Response Group service-** Cliquez sur le bouton **avancé** , puis spécifiez les URI des groupes de réponse que vous avez déjà créés lors de la mise en service de Response Group agent services. Vous devez choisir au moins un groupe de réponse. Pour en utiliser davantage, séparez les groupes de réponses par des points-virgules. Mettez à jour **RGSUriSuffixStartIndex** et **RGSUriSuffixEndIndex** sur les valeurs réelles. Choisissez un niveau de charge.
    
- **Services d’information d’emplacement-** Sélectionnez un niveau de charge activé ou désactivé.
    
> [!NOTE]
> Chacun des scénarios comporte un bouton avancé qui s’affiche à côté de celui-ci, ainsi qu’un ensemble de cases à cocher permettant d’utiliser des variantes du paramètre par défaut. 
  
- Le choix d' *ad-hoc* permettra à l’outil de générer une simulation de conférences qui seront créées tout au long de l’heure.
    
- Le choix de l’option *grande conf* signifie qu’un scénario de conférence de grande taille sera simulé.
    
-  *Externe* indique à l’outil qu’il doit également simuler des utilisateurs externes.
    
Ces boutons et cases à cocher sont des valeurs supplémentaires spécifiques à chaque scénario, qui changeront le comportement de l’outil de stress et de performance et permettent la personnalisation possible.
  
Pour chaque scénario sous l’onglet scénarios généraux (à l’exception de services d’information d’emplacement), si la valeur de niveau de charge est **personnalisé**, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue avancé. Le nom du champ peut varier en fonction du scénario, mais la description du champ indique : *Remarque ce numéro sera uniquement utilisé si personnalisé est sélectionné dans le menu déroulant* .
  
Les valeurs **élevé**, **moyen**et **faible**modifient les taux de conversation par modalité en fonction du modèle utilisateur qui est un bilan de l’ensemble des scénarios. S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence d’utilisation prévue, utilisez un taux de conversation personnalisé.
  
#### <a name="voice-scenarios-tab"></a>Onglet scénarios vocaux

Il s’agit de l’onglet permettant de configurer tous les scénarios relatifs à la voix.
  
![Chargez l’onglet Scénarios vocaux de l’outil de configuration.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Les options disponibles sont les suivantes :
  
- **VoIP-** Cliquez sur le bouton **avancé** et ajoutez des valeurs pour les champs PhoneAreaCode et LocationProfile (plan de numérotation). Vous pouvez également attribuer une valeur au niveau de charge. Si vous choisissez un niveau de charge pour le protocole VoIP ou la passerelle RTC (réseau téléphonique commuté), un fichier de configuration de réseau téléphonique commuté (PSTN) vers des communications unifiées (UC) est généré pour simuler les appels externes.
    
- **UC/passerelle RTC-** Vous devez choisir une valeur de niveau de charge et, lorsque vous choisissez une autre option que désactivé, vous devez fournir une valeur pour le code de zone RTC en cliquant sur le bouton **avancé** . Cliquez sur **Ajouter** sous le serveur de médiation et sur PSTN. Vérifiez que vous disposez d’un itinéraire configuré pour l’indicatif régional.
    
    > [!TIP]
    > Vous pouvez utiliser le panneau de configuration Skype pour les entreprises ou le shell de gestion de Skype entreprise pour vérifier la configuration de votre gamme vocale. 
  
- **Surveillant de conférences-** Fournissez une valeur pour le niveau de charge. Toute valeur autre que Disabled active le champ **numéro de téléphone** . Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser. Cliquez sur **avancé** et attribuez une valeur au champ **LocationProfile** .
    
- **Service de stationnement d’appel-** Dans cette section, fournissez un niveau de charge.
    
- **Serveur de médiation et RTC** Chaque serveur de médiation que vous souhaitez utiliser a besoin de son propre simulateur PSTN. Une fois que vous avez déterminé le client que vous allez utiliser pour le simulateur, configurez votre serveur de médiation pour router les appels vers cet ordinateur sur le simulateur PSTN que vous avez configuré. Cliquez sur le bouton **Ajouter** pour configurer une valeur pour le serveur de médiation.
    
    > [!NOTE]
    > Un bouton avancé est placé en regard de chaque scénario. Les boîtes de dialogue avancées contiennent des paramètres spécifiques à chaque scénario qui modifient le comportement de l’outil de stress et de performance, et activent la personnalisation. > pour chaque scénario sous l’onglet scénarios vocaux, si la valeur de niveau de charge est **personnalisée**, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue avancé. Le nom du champ peut varier en fonction du scénario, mais la description du champ indique : *Remarque ce numéro sera uniquement utilisé si personnalisé est sélectionné dans le menu déroulant* .
  
#### <a name="web-app-tab"></a>Onglet application Web

![Chargez l’onglet Application web de l’outil de configuration.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App prend en charge les scénarios de conférence par le biais du serveur UCWA (Unified Communications Web API) installé sur un serveur frontal. Utilisez l’onglet Web App pour configurer tous les scénarios liés à une application Web. Les options disponibles sont les suivantes :
  
- **Paramètres généraux de l’application Web-** Cliquez sur le bouton **paramètres supplémentaires** et définissez **ReachTargetServerUrl** sur l’adresse IP virtuelle de la liste d’annuaires.
    
- **Partage d’application** Sélectionnez une valeur pour niveau de charge.
    
- **Collaboration sur les données :** Sélectionnez une valeur pour niveau de charge.
    
- **Messagerie instantanée-** Sélectionnez une valeur pour niveau de charge.
    
- **Conférence vocale-** Sélectionnez une valeur pour niveau de charge.
    
> [!NOTE]
> Dans chacun des scénarios, un bouton **avancé** est placé en regard. Les boîtes de dialogue avancées contiennent des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance et permettent la personnalisation. > pour chaque scénario d’application Web, si le niveau de charge est **personnalisé**, la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée à la place de la valeur par défaut.
  
#### <a name="mobility-tab"></a>Onglet mobilité

Utilisez cet onglet pour configurer tous les scénarios liés à la mobilité.
  
![Chargez l’onglet Mobilité de l’outil de configuration.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Les options disponibles sont les suivantes :
  
- **Paramètres de mobilité généraux-** Cliquez sur **paramètres supplémentaires** , puis définissez le champ UcwaTargetServerUrl sur l’adresse IP virtuelle du pool de réalisateurs ou le protocole VIP de pool frontal.
    
- **Présence et messagerie instantanée P2P/audio-** Sélectionnez une valeur pour niveau de charge pour activer la simulation de mobilité.
    
> [!NOTE]
> Dans chacun des scénarios, un bouton **avancé** est placé en regard. Les boîtes de dialogue avancées contiennent des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance et permettent la personnalisation. > pour chacun des scénarios de mobilité, si le niveau de charge est **personnalisé**, la valeur spécifiée dans le champ **ConversationsPerHour** est utilisée à la place de la valeur par défaut.
  
#### <a name="summary-tab"></a>Onglet Résumé

L’onglet Résumé indique quels utilisateurs utiliser pour chacun des scénarios.
  
![Chargez l’onglet Résumé de l’outil de configuration.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
L’onglet Résumé indique quels utilisateurs utiliser pour chacun des scénarios. 
  
Il est possible de configurer manuellement les plages de numéros d’utilisateur en activant la case à cocher **activer la génération de plage d’utilisateurs personnalisés** , puis en double-cliquant sur le scénario dans la table dont vous souhaitez personnaliser la plage d’utilisateurs.
  
Vérifier **(RunClient. bat) ajoutez un délai de connexion lorsque vous commencez** à inclure des retards dans les fichiers de commandes générés pour correspondre au taux de connexion. Cela peut s’avérer utile pour éviter une surcharge du serveur lors de la connexion d’un grand nombre d’utilisateurs.
  
Cliquez sur **générer des fichiers** , puis sélectionnez le dossier dans lequel vous voulez générer la configuration. Une boîte de dialogue s’affiche lors de la création de vos fichiers.
  
![Message « Les fichiers de configuration ont été générés correctement ». Cliquez sur OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Exécuter LyncPerfTool
<a name="BKMK_RunTool"> </a>

Pour exécuter l’outil de stress et performance de Skype entreprise Server 2015, vous devez créer des utilisateurs, des contacts et des scénarios. Pour plus d’informations sur l’utilisation des outils pour effectuer ces actions, voir [créer des utilisateurs et des contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) et [configurer le profil d’utilisateur](using-the-tool.md#BKMK_UserProfile) précédemment dans cet article. L’exécution de ces outils génère également un fichier qui sera exécuté à l’aide de l’outil de stress et de performance dans le cadre d’un fichier de commandes avec les paramètres nécessaires inclus.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Exécution de l’outil de stress et de performance de Skype entreprise Server 2015

L’outil de configuration de charge (UserProfileGenerator. exe) crée un fichier de commandes qui vous permet d’exécuter l’outil de stress et de performance (LyncPerfTool. exe) en inscrivant les compteurs de performance et en chargeant le fichier de configuration XML. Le fichier de commandes exécute une instance de LyncPerfTool. exe par fichier de configuration. Pour exécuter le fichier de commandes, procédez comme suit :
  
### <a name="run-the-stress-and-performance-test"></a>Exécuter le test de stress et de performance

1. Copiez le dossier avec les dossiers de configuration et les fichiers dans le répertoire contenant LyncPerfTool. exe sur chaque ordinateur client. Par exemple, si vous avez généré les fichiers de configuration dans le dossier nommé 1.28 _ 13.16.16, copiez ce dossier dans le dossier contenant LyncPerfTool. exe. Procédez ainsi pour chaque client.)
    
2. Accédez au dossier client et exécutez le script de commande **RunClient** . Vous pouvez double-cliquer sur le fichier de commandes dans l’Explorateur Windows pour exécuter tous les fichiers de configuration pour ce client. Vous pouvez également exécuter le script à partir d’un dossier client en utilisant la syntaxe suivante :
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Pour exécuter l’outil de stress et de performance directement, ouvrez une invite de commandes et tapez la commande suivante à partir de la ligne de commande (et lorsque vous effectuez cette opération pour la première fois, `regsvr32 /i /n /s LyncPerfToolPerf.dll`veillez à enregistrer les compteurs de performance, comme indiqué dans la note plus loin dans cette rubrique) :
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Pour que l’outil affiche les valeurs du fichier de configuration, incluez `/displayfile` le paramètre sur la commande précédente de sorte qu’il se présente comme suit :
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Pour *mettre fin* au processus, appuyez sur Ctrl + C.
  
> [!NOTE]
> Avant d’exécuter directement l’outil de stress et de performance, vous devez inscrire les compteurs de performance à l’aide de la commande suivante :`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Toutes les instances de l’outil de stress et de performance que vous commencez à commencer immédiatement à se connecter aux utilisateurs, en général à un tarif d’un utilisateur par seconde. 
  
Le taux de connexion de l’utilisateur pointe pour le pool est d’environ 12 par seconde. Cela signifie que vous ne devez pas démarrer plus de 12 instances LyncPerfTool. exe en même temps lorsque les utilisateurs sont toujours en cours de connexion. 1000 utilisateurs de plus de 20 minutes peuvent se connecter complètement à une seconde.
  
## <a name="interpreting-the-results"></a>Interprétation des résultats
<a name="BKMK_Interpret"> </a>

L’outil de stress et de performance de Skype entreprise Server 2015 comporte de nombreux compteurs qui peuvent vous aider à comprendre ce que fait le client et déterminer s’il rencontre des problèmes.
  
### <a name="client-counters"></a>Compteurs clients

Chaque instance de LyncPerfTool. exe en cours d’exécution dispose d’une instance distincte des compteurs. Chaque instance est nommée par son ID de processus. Si les clients sont surchargés, d’autres problèmes peuvent se produire. Pour éviter ces problèmes :
  
- Surveiller l’utilisation du processeur et de la mémoire sur les ordinateurs clients. Si le processeur est toujours supérieur à 90%, réduisez le nombre d’utilisateurs.
    
- Lorsque l’encombrement mémoire est élevé, vous risquez de rencontrer des problèmes si le fichier de la page commence à manquer d’espace. Assurez-vous que la mémoire de validation n’atteint pas la limite de l’ordinateur. Si vous utilisez des limites de mémoire, envisagez d’augmenter la taille du fichier de page ou de réduire le nombre d’utilisateurs.
    
Voici une liste de compteurs de performance clés :
  
**Informations générales**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Temps passé en minutes  <br/> |Temps passé depuis le démarrage du processus.  <br/> |
|Points de terminaison actifs  <br/> |Nombre de points de terminaison actuellement connectés au serveur.  <br/> |
|Échecs de connexion  <br/> |Nombre total d’échecs de connexion de point de terminaison.  <br/> |
|Tentatives d’ouverture de session  <br/> |Nombre total de tentatives de connexion de point de terminaison.  <br/> |
|Points de terminaison déconnectés  <br/> |Nombre total de points de terminaison qui ont été déconnectés.  <br/> |
   
**Informations de présence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels SetPresence  <br/> |Nombre total de tentatives de changement de présence. Pour les différents types de modifications de présence, voir le compteur de performance appels SetPresence (type de présence).  <br/> |
|NNN réponses pour SetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Appels GetPresence  <br/> |Nombre total de tentatives de demande de présence.  <br/> |
|NNN réponses pour GetPresence  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
   
**Informations relatives au service de carnet d’adresses**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Tentatives de téléchargements de fichiers complets/Delta de ABS  <br/> |Nombre total de demandes de téléchargement de fichiers complets ou Delta.  <br/> |
|Réussite des téléchargements de fichiers complets/Delta  <br/> |Nombre total de demandes de téléchargement de fichiers complets ou Delta.  <br/> |
|Compteurs liés au service de requête Web dans le carnet d’adresses  <br/> |Compteurs liés au téléchargement du fichier du carnet d’adresses.  <br/> |
|Tentatives d’appels WS WS  <br/> |Nombre total de demandes de service de requête Web dans le carnet d’adresses.  <br/> |
|Appels WS WS réussis  <br/> |Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse réussi.  <br/> |
|Échecs des services d’ABS WS  <br/> |Nombre total de demandes de service de requête Web de carnet d’adresses qui renvoient un code de réponse d’erreur.  <br/> |
   
> [!NOTE]
> Cette catégorie inclut des compteurs permettant de surveiller les téléchargements de fichiers du service de carnet d’adresses et les demandes de service de requête sur le carnet d’adresses. 
  
**Informations de liste de distribution (DL)**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels essayés  <br/> |Nombre total de demandes de service Web d’extension de liste de distribution (DLX) effectuées.  <br/> |
|Appels réussis  <br/> |Nombre total de demandes de service Web DLX ayant renvoyé un code de réponse réussi.  <br/> |
|Appels en échec  <br/> |Nombre total de demandes de service Web DLX qui renvoient un code de réponse d’erreur.  <br/> |
   

  
> [!NOTE]
> Les compteurs de performance indiqués ci-dessous indiquent les numéros de tous les appels voix sur IP (VoIP), y compris les appels vers le serveur de médiation, le serveur de conférence A/V, le serveur Edge, l’application Response Group et le standard automatique des conférences, lorsque ces scénarios sont activés. 
  
**Informations de base sur VoIP**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels vocaux entrants/sortants actuellement en cours.  <br/> |
|Appels interrompus  <br/> |Nombre total d’appels vocaux entrants/sortants déjà terminés.  <br/> |
|Appels refusés  <br/> |Nombre total d’appels vocaux entrants refusés.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels vocaux entrants/sortants.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels vocaux entrants/sortants établis.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Taux de passe VoIP (%)  <br/> |Nombre total d’appels passés/nombre total d’appels tentés.  <br/> |
   
**Informations de l’appel service de Response Group**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels actifs vers l’application Response Group.  <br/> |
|Appels essayés  <br/> |Nombre total d’appels tentés.  <br/> |
   
**Informations sur les appels de messagerie instantanée**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de messages instantanés entrants et sortants.  <br/> |
|Appels interrompus  <br/> |Nombre total d’appels entrants/sortants de messagerie instantanée déjà terminés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Messages INSTANTANÉs reçus/envoyés  <br/> |Nombre total de messages reçus ou envoyés pour toutes les sessions.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels entrants/sortants de messages instantanés.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels entrants/sortants de messages instantanés établis.  <br/> |
   
**Informations sur les appels de partage d’application**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels de partage d’application entrants ou sortants.  <br/> |
|Appels interrompus  <br/> |Nombre total d’appels de partage d’application entrants/sortants déjà terminés.  <br/> |
|Appels reçus NNN  <br/> |Nombre total de codes de réponse nnn reçus du serveur.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels entrants/sortants de partage d’application.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels de partage d’application entrants/sortants établis.  <br/> |
   
**Informations sur les appels CAA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Appels actifs  <br/> |Nombre total d’appels entrants/sortants de réseau téléphonique commuté (RTC) actuellement en cours.  <br/> |
|Appels interrompus  <br/> |Nombre total d’appels RTC entrants/sortants déjà terminés.  <br/> |
|Tentatives d’appels entrants/sortants  <br/> |Nombre total d’appels RTC entrants et sortants.  <br/> |
|Appels entrants/sortants établis  <br/> |Nombre total d’appels RTC entrants/sortants établis.  <br/> |
   
**Informations sur la Conférence**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Conférences de messagerie instantanée actives  <br/> |Nombre total de conférences de messagerie instantanée en cours.  <br/> |
|Conférences audio/vidéo actives  <br/> |Nombre total de conférences audio/vidéo (A/V) en cours.  <br/> |
|Conférences de partage d’application actives  <br/> |Nombre total de conférences de partage d’application en cours.  <br/> |
|Nombre de participants  <br/> |Nombre total de participants actuellement connectés aux conférences.  <br/> |
|Échec de la planification de conférences  <br/> |Nombre total d’échecs lors de la planification d’une conférence.  <br/> |
|Participer à une conférence téléphonique  <br/> |Nombre total d’échecs lors d’une tentative de connexion à une conférence.  <br/> |
   
**Compteurs du client UCWA**

|**Compteur de performance**|**Description**|
|:-----|:-----|
|Nombre total de jointures IMMCU réussies  <br/> |Nombre total de conférences de messagerie instantanée jointes.  <br/> |
|Nombre total de jointures DMCU réussies  <br/> |Nombre total de conférences A/V jointes.  <br/> |
   

