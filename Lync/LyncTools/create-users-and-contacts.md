---
title: Créer des utilisateurs et des contacts
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f09ac6fd667b77b47e27ec9fb9caac44b9a13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Créer des utilisateurs et des contacts

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Vous devez utiliser l’outil de mise en service des utilisateurs de Lync Server 2013 (UserProvisioningTool. exe) pour créer des utilisateurs et des contacts en préparation au test de charge de stress et de performance.

Vous trouverez ci-dessous une liste de termes et de définitions qui peuvent vous intéresser lorsque vous lisez ce sujet.

  - Unité d’organisation-l’unité d’organisation Active Directory Domain Services (UO).

  - Regroupement fédéré/croisé: les utilisateurs qui pourront communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée, tels que le réseau MSN de services Internet, le® AOL et Yahoo\!®.

  - Listes de distribution: objets dans les services de domaine Active Directory (AD FS) qui contiennent une liste des utilisateurs des services de domaine Active Directory (AD FS) utilisés pour le lancement des communications avec des groupes de personnes.

  - Service des informations de géolocalisation: le service Lync Server 2013 qui, lorsqu’il est activé ou configuré par téléphone, autorise la récupération de l’emplacement physique pour les services Enhanced 9-1-1 (E9-1-1).

  - Numéros de téléphone américains: les numéros de téléphone affectés aux utilisateurs, en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants et la recherche de numéros inversés (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool. exe

Vous devez utiliser l’outil de mise en service de l’utilisateur de Lync Server pour créer des utilisateurs et des contacts pour la simulation de chargement. L’outil de mise en service de l’utilisateur Lync Server est installé avec le package d’outils de stress et de performance de Lync Server. Assurez-vous que le programme d’installation de package (CapacityPlanningTool. msi) a été exécuté sur le serveur frontal ou sur le serveur Standard Edition Server. Démarrez l’outil de mise en service de l’utilisateur Lync Server en exécutant le fichier UserProvisioningTool. exe (qui se trouve\\à% InstalledDirectory% LyncStressAndPerfTool LyncStress) sur le serveur frontal ou sur le serveur Standard Edition Server.

<div>


> [!IMPORTANT]  
> Vous devez être connecté en tant que membre du groupe de sécurité administrateurs de domaine pour pouvoir exécuter UserProvisioningTool. exe. Il est nécessaire de procéder à une exécution à partir du contexte, car UserProvisioningTool. exe crée et configure de nouveaux utilisateurs de services de domaine Active Directory.



</div>

<div>


> [!NOTE]  
> Lorsque vous créez un nombre d’utilisateurs important (10 000 ou plus), exécutez UserProvisioningTool. exe à partir d’un ordinateur haut de gamme. Notez que le contrôleur de domaine fonctionne également en charge lors de la création des utilisateurs.



</div>

Lorsque l’outil de mise en service de l’utilisateur Lync Server s’ouvre, cliquez sur **configuration** , puis sélectionnez **charger la configuration**. Pour commencer à configurer les utilisateurs et les contacts, chargez le fichier par défaut inclus dans le package, SampleData. Xml. Cette opération préremplira les champs avec des exemples de données que vous devrez modifier pour votre système. Si vous avez un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, chargez ce fichier à la place. Renseignez les champs de l’outil de mise en service de l’utilisateur Lync Server, comme décrit dans les sections suivantes.

![Onglet création d’utilisateur.] (images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Onglet création d’utilisateur.")

Pour configurer les options du serveur, procédez comme suit.

1.  Dans nom de domaine complet (FQDN) du **pool frontal**, tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou du pool frontal sur lequel vous souhaitez héberger les utilisateurs.

2.  Dans **nom d’utilisateur**, entrez le préfixe que vous souhaitez utiliser pour créer des noms d’utilisateur à des fins de test.

3.  Dans **mot de passe**, spécifiez un mot de passe qui sera appliqué à tous les comptes d’utilisateurs de test.

4.  Dans **domaine SIP**, tapez le nom de domaine à utiliser pour les URI SIP des utilisateurs test (Uniform Resource Identifiers).

5.  Dans **domaine de compte**, tapez le nom de domaine de votre domaine de services de domaine Active Directory actuel, sous lequel vous voulez créer les utilisateurs de test.

6.  Dans **unité d’organisation**, tapez le nom de l’unité d’organisation Active Directory Domain Services dans laquelle vous voulez créer les objets utilisateur. S’il n’existe pas, il sera créé.

7.  Dans **Code de la zone téléphonique**, tapez le code de zone à trois chiffres qui sera utilisé pour les comptes d’utilisateurs test. Assurez-vous que le code de zone téléphonique n’entre pas en conflit avec les codes de zone des autres utilisateurs dans les services de domaine Active Directory.

8.  Activez la case à cocher **voix activée** si vous souhaitez activer l’option voix entreprise pour les utilisateurs de test.

9.  Dans **nombre d’utilisateurs**, spécifiez le nombre total d’utilisateurs de test que vous souhaitez créer.

10. Dans **index de début**, spécifiez le numéro de départ qui sera utilisé comme suffixe du préfixe du nom d’utilisateur.

<div>

## <a name="create-users-button"></a>Bouton créer des utilisateurs

Lorsque vous cliquez sur le bouton créer des utilisateurs, tous les paramètres d’entrée sont validés.

  - S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.

  - Si toutes les valeurs d’entrée sont correctes, la création des utilisateurs dans les services de domaine Active Directory va commencer. Une barre de progression apparaît au bas du formulaire. Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.

Le processus de création d’utilisateur est lent. Quelques minutes peuvent être nécessaires. Si le nombre d’utilisateurs est très grand, le processus peut même prendre quelques heures. Si les utilisateurs existent déjà, ils sont mis à jour avec les modifications apportées. Vous pouvez vérifier que les utilisateurs ont été créés en se connectant comme l’un des utilisateurs de la plage. Utilisez le préfixe d’utilisateur, le numéro d’utilisateur et le @sipDomain comme nom d’utilisateur (par exemple, LyncUser10@contoso.net), ainsi que le mot de passe spécifié.

</div>

<div>

## <a name="delete-users-button"></a>Bouton supprimer des utilisateurs

Lorsque vous cliquez sur le bouton supprimer des utilisateurs, tous les paramètres d’entrée sont validés.

  - S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.

  - Si toutes les valeurs d’entrée sont correctes, elles commenceront à désactiver et à supprimer des utilisateurs dans les services de domaine Active Directory (AD FS). Une barre de progression apparaît au bas du formulaire. Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Seuls les numéros de téléphone au format U.S. sont pris en charge. Les numéros de téléphone sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool. exe sont activés pour Enterprise Voice. Tout scénario utilisant le numéro de téléphone, comme le standard automatique des conférences ou les appels RTC, utilisez ce numéro de téléphone pour acheminer correctement les appels. C’est pourquoi chaque utilisateur doit avoir un numéro de téléphone unique. Si vous devez créer des utilisateurs à deux reprises, la commande échouera, sauf si vous utilisez un indicatif de zone différent ou si les utilisateurs précédents ont été désactivés à l’aide de l’applet de commande <STRONG>Disable-Csuser</STRONG> .</P>
> <LI>
> <P>Avant de créer des contacts, vous devez commencer par procéder à la réplication des utilisateurs, à partir de l’onglet utilisateurs. Si vous venez de créer vos utilisateurs, vous devez attendre la fin de la réplication de Lync Server et remplir les comptes d’utilisateurs dans la base de données. Si les utilisateurs n’ont pas terminé la réplication, un message d’erreur s’affiche. Vous savez alors que les utilisateurs ont fini de procéder à la réplication si le service frontal de Lync Server 2013 a démarré ou en exécutant correctement l’applet de passe <STRONG>Get-Csuser</STRONG> sur le dernier utilisateur.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Onglet Création de contacts

L’onglet Création de contacts vous permet de spécifier les détails des contacts des utilisateurs.

![Onglet Création de contacts.] (images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Onglet Création de contacts.")

Pour configurer les contacts des utilisateurs, procédez comme suit.

1.  Dans les contacts moyens par utilisateur, spécifiez le nombre moyen de contacts à renseigner dans les listes de contacts pour chacun des utilisateurs.

2.  Activez la case à cocher fixe si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous voulez modifier le nombre de contacts créés pour les utilisateurs, décochez la case.

3.  Dans les groupes de contacts moyens par utilisateur, spécifiez le nombre de groupes de contacts par utilisateur. Ce numéro doit être inférieur à la moyenne des contacts par utilisateur.

4.  Dans la section pourcentage du nombre de contacts du pool fédéré/du groupe croisé, spécifiez un nombre compris entre 0 et 100. Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.

5.  Dans le cas d’un préfixe d’utilisateur pour les pools fédéré et Cross, spécifiez le nom d’utilisateur des utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.

6.  Dans domaine SIP pour les utilisateurs fédérés/ThreadPool, spécifiez le nom de domaine SIP des utilisateurs fédérés.
    
    <div>
    

    > [!NOTE]  
    > Aucun utilisateur ne doit être connecté lors de la création de contacts.

    
    </div>

7.  Dans l’onglet création d’utilisateur, vérifiez que les paramètres sont corrects. Le nombre d’utilisateurs pour lesquels les contacts seront créés est obtenu à partir de l’onglet création d’utilisateurs.

8.  Cliquez sur créer des contacts pour commencer la création du contact. Ce processus peut prendre quelques minutes. Une fois qu’elle est terminée, une boîte de dialogue s’affiche avec le message «opération terminée correctement». Vous pouvez valider les contacts créés en vous connectant en tant qu’utilisateur créé à partir de l’onglet création d’utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Une fois les contacts créés, vous redémarrez tous les serveurs frontaux dans la liste cible. Le début de la période (jusqu’à 2 heures) est susceptible de durer plus longtemps, selon le nombre de contacts créés par cette opération.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Liste de distribution

L’une des fonctionnalités de l’outil de stress et de performance de Lync Server 2013 consiste à simuler la fonctionnalité d’extension de liste de distribution dans Lync 2013. Si vous n’êtes pas en mesure d’activer l’extension DL dans UserProvisioningTool, vous pouvez ignorer cette étape.

![Onglet Création de liste de distribution.] (images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Onglet Création de liste de distribution.")

L’onglet Liste de distribution vous permet de créer des listes de distribution que l’outil de stress et de performance utilisera pour la fonctionnalité d’extension de liste de distribution. Avant de créer des listes de distribution, Lync Server 2013 doit déjà être installé. Vous devez avoir exécuté Lync Server 2013 ForestPrep. Dans le cas contraire, les attributs DL n’existent pas dans le schéma des services de domaine Active Directory et l’outil ne peut pas créer de DL.

Pour configurer des listes de distribution, procédez comme suit.

1.  Dans nombre de listes de distribution, spécifiez le nombre total de DL que vous souhaitez créer. (Nous vous recommandons d’utiliser deux fois le nombre d’utilisateurs). Ils sont numérotés de 0 à n-1.

2.  Dans préfixe de la liste de distribution, spécifiez le préfixe de la liste de distribution. Par exemple, si vous spécifiez des listes de distribution 100 et un préfixe de testDL, les listes de distribution seront nommées testDL0, testDL1, etc., via testDL99.

3.  Dans membres minimum d’une liste de dist., spécifiez le nombre minimum d’utilisateurs à ajouter dans chaque liste de distribution.

4.  Dans nombre maximal de membres d’une liste de dist., spécifiez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.

<div>

## <a name="create-distribution-lists-button"></a>Bouton créer des listes de distribution

Lorsque vous cliquez sur le bouton créer des listes de distribution, l’outil interroge les services de domaine Active Directory pour voir si les listes de distribution correspondant au préfixe et aux numéros existent déjà. L’outil crée uniquement ceux qui n’existent pas déjà. Lors de l’ajout de membres à ces listes de distribution nouvellement créées, les utilisateurs sont sélectionnés dans la plage spécifiée dans l’onglet création d’utilisateurs.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Onglet Configuration du service informations de géolocalisation

L’une des fonctionnalités de l’outil de stress et de performance de Lync Server 2013 consiste à générer des fichiers de configuration factices pour le service d’information d’emplacement. En règle générale, le service des informations d’emplacement n’a pas d’impact important sur les performances sur les serveurs.

![Onglet Configuration du service informations] de géolocalisation. (images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Onglet Configuration du service informations") de géolocalisation.

Si vous choisissez de tester cette fonctionnalité, vous pouvez renseigner les valeurs mentionnées dans le formulaire, puis cliquer sur le bouton générer les fichiers de configuration de LIS. Il génère des fichiers CSV nommés LIS\_subnet. csv, lis\_switchs. csv,\_lis ports. csv et lis\_WAP. csv. Vous pouvez ensuite importer ces fichiers CSV dans la base de données LIS à l’aide de l’applet de cmdlet **Set-CsLisSubnet** , de l’applet de applet Set- **CsLisSwitch** , de l’applet de passe **Set-CsLisPort** et de l’applet **de passe Set-CsWirelessAccessPoint** , respectivement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

