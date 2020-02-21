---
title: Créer des utilisateurs et des contacts
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b8016079cd130a814da410df5e5a5b151d8702
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Créer des utilisateurs et des contacts

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Vous devez utiliser l’outil de mise en service utilisateur Lync Server 2013 (UserProvisioningTool. exe) pour créer des utilisateurs et des contacts en vue de préparer le test de charge de stress et de performances.

Voici une liste des termes et des définitions que vous pouvez trouver utiles lors de la lecture de cette rubrique.

  - Unité d’organisation : l’unité d’organisation des services de domaine Active Directory.

  - Fédérés/interpools : utilisateurs qui seront autorisés à communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée, tels que MSN Network of Internet Services, AOL® et Yahoo\!®.

  - Listes de distribution : objets des services de domaine Active Directory qui contiennent une liste des utilisateurs des services de domaine Active Directory, utilisés pour lancer des communications avec des groupes de personnes.

  - Service d’informations d’emplacement : le service Lync Server 2013 qui, lorsqu’il est activé et configuré par téléphone, permet la récupération de l’emplacement physique des services Enhanced 9-1-1 (E9-1-1).

  - Numéros de téléphone des États-Unis : numéros de téléphone affectés aux utilisateurs, en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants et la recherche de numéros inversées (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool. exe

Vous devez utiliser l’outil de mise en service d’utilisateur Lync Server pour créer des utilisateurs et des contacts pour la simulation de charge. L’outil de mise en service des utilisateurs Lync Server est installé avec le package d’outils de performances et de stress de Lync Server. Assurez-vous que le programme d’installation du package (CapacityPlanningTool. msi) a été exécuté sur le serveur frontal ou le serveur Standard Edition. Démarrez l’outil de mise en service des utilisateurs Lync Server en exécutant le fichier UserProvisioningTool. exe (situé dans le dossier\\% InstalledDirectory% LyncStressAndPerfTool LyncStress) sur le serveur frontal ou sur le serveur Standard Edition Server.

<div>


> [!IMPORTANT]  
> Vous devez être connecté en tant que membre du groupe de sécurité administrateurs du domaine afin d’exécuter UserProvisioningTool. exe. Il est nécessaire d’exécuter à partir de ce contexte car UserProvisioningTool. exe crée et configure les nouveaux utilisateurs des services de domaine Active Directory.



</div>

<div>


> [!NOTE]  
> Lorsque vous créez un nombre important d’utilisateurs (10 000 ou plus), exécutez UserProvisioningTool. exe à partir d’un ordinateur haut de gamme. Notez que le contrôleur de domaine subira également une charge élevée pendant que les utilisateurs sont en cours de création.



</div>

Lorsque l’outil de mise en service de l’utilisateur Lync Server s’ouvre, cliquez sur **configuration** , puis sélectionnez **charger la configuration**. Pour commencer à configurer des utilisateurs et des contacts, chargez le fichier par défaut inclus dans le package, SampleData. Xml. Cette opération préremplira les champs avec des exemples de données que vous devrez réviser pour votre système. Si vous disposez d’un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, chargez ce fichier à la place. Renseignez les champs de l’outil de mise en service d’utilisateur Lync Server, comme décrit dans les sections suivantes.

![Onglet création d’utilisateur.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Onglet création d’utilisateur.")

Pour configurer les options de serveur, procédez comme suit.

1.  Dans nom de domaine **complet du pool frontal**, tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou du pool frontal où vous voulez héberger les utilisateurs.

2.  Dans **préfixe du nom d’utilisateur**, tapez un préfixe que vous souhaitez utiliser pour créer des noms d’utilisateurs à des fins de test.

3.  Dans **mot de passe**, spécifiez un mot de passe qui sera appliqué à tous les comptes d’utilisateur test.

4.  Dans **domaine SIP**, tapez le nom de domaine à utiliser pour les URI SIP (Uniform Resource Identifiers) des utilisateurs test.

5.  Dans **domaine de compte**, tapez le nom de domaine de votre domaine des services de domaine Active Directory actuel, sous lequel vous souhaitez créer les utilisateurs de test.

6.  Dans **unité d’organisation**, tapez le nom de l’unité d’organisation des services de domaine Active Directory dans laquelle vous souhaitez créer les objets utilisateur. Si l’unité d’organisation n’existe pas, elle sera créée.

7.  Dans **Code de zone de téléphone**, tapez le code de zone à trois chiffres qui sera utilisé pour les comptes d’utilisateur test. Assurez-vous que le code de la zone téléphonique n’entre pas en conflit avec les autres codes de zone des utilisateurs dans les services de domaine Active Directory.

8.  Activez la case à cocher **voix activée** si vous souhaitez activer les utilisateurs de test pour voix entreprise.

9.  Dans **nombre d’utilisateurs**, spécifiez le nombre total d’utilisateurs test que vous souhaitez créer.

10. Dans **index de début**, spécifiez le numéro de départ qui sera utilisé comme suffixe du préfixe du nom d’utilisateur.

<div>

## <a name="create-users-button"></a>Bouton créer des utilisateurs

Lorsque vous cliquez sur le bouton créer des utilisateurs, il valide tous les paramètres d’entrée.

  - S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.

  - Si toutes les valeurs d’entrée sont correctes, il commence à créer des utilisateurs dans les services de domaine Active Directory. Une barre de progression s’affiche au bas de ce formulaire. Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.

La création de l’utilisateur est un processus lent. Cette opération peut prendre plusieurs minutes. Si le nombre d’utilisateurs est très important, le processus peut prendre quelques heures. Si les utilisateurs existent déjà, ils sont mis à jour avec les modifications. Vous pouvez vérifier que les utilisateurs ont été créés en ouvrant une session en tant que l’un des utilisateurs de la plage. Utilisez le préfixe d’utilisateur, le numéro d’utilisateur et le @sipDomain comme nom d’utilisateur (par exemple, LyncUser10@contoso.net), ainsi que le mot de passe spécifié.

</div>

<div>

## <a name="delete-users-button"></a>Bouton supprimer des utilisateurs

Lorsque vous cliquez sur le bouton supprimer des utilisateurs, il valide tous les paramètres d’entrée.

  - S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.

  - Si toutes les valeurs d’entrée sont correctes, il commencera à désactiver et à supprimer les utilisateurs dans les services de domaine Active Directory. Une barre de progression s’affiche au bas de ce formulaire. Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Seuls les numéros de téléphone au format américain sont pris en charge. Les numéros de téléphone sont toujours attribués aux utilisateurs et tous les utilisateurs créés par UserProvisioningTool. exe sont activés pour voix entreprise. Tous les scénarios qui utilisent le numéro de téléphone, comme les appels de standard automatique de conférence ou RTC-PSTN, utilisent ce numéro de téléphone pour acheminer correctement les appels. Pour cette raison, chaque utilisateur doit disposer d’un numéro de téléphone unique. Si vous devez créer des utilisateurs à deux reprises, la commande échoue, sauf si vous utilisez un indicatif régional différent ou si les utilisateurs précédents ont été désactivés à l’aide de la cmdlet <STRONG>Disable-Csuser</STRONG> .</P>
> <LI>
> <P>Avant de créer des contacts, vous devez d’abord effectuer une réplication utilisateur, effectuée à partir de l’onglet utilisateurs. Si vous venez de créer vos utilisateurs, vous devez patienter jusqu’à ce que la réplication Lync Server se termine et renseigne les comptes d’utilisateur dans la base de données. Si les utilisateurs n’ont pas terminé la réplication, un message d’erreur s’affiche. Vous saurez quand les utilisateurs ont terminé la réplication si le service frontal Lync Server 2013 a démarré ou en exécutant correctement la cmdlet <STRONG>Get-Csuser</STRONG> sur le dernier utilisateur.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Onglet Création de contacts

L’onglet Création de contacts vous permet de spécifier les détails des contacts des utilisateurs.

![Onglet Création de contacts.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Onglet Création de contacts.")

Pour configurer les contacts des utilisateurs, procédez comme suit.

1.  Dans moyenne des contacts par utilisateur, spécifiez le nombre moyen de contacts à remplir dans les listes de contacts pour chacun des utilisateurs.

2.  Activez la case à cocher fixe si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur. Si vous souhaitez modifier le nombre de contacts créés pour les utilisateurs, désactivez la case à cocher.

3.  Dans moyenne des groupes de contacts par utilisateur, spécifiez le nombre de groupes de contacts par utilisateur. Ce nombre doit être inférieur à la moyenne des contacts par utilisateur.

4.  Dans le pourcentage de contacts fédérés/de pool croisé, spécifiez un nombre compris entre 0 et 100. Ce pourcentage de contacts est créé avec les utilisateurs fédérés.

5.  Dans le préfixe d’utilisateur fédéré/de pool croisé, spécifiez le nom d’utilisateur des utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.

6.  Dans domaine SIP d’utilisateur fédéré/de pool croisé, spécifiez le nom de domaine SIP des utilisateurs fédérés.
    
    <div>
    

    > [!NOTE]  
    > Aucun utilisateur ne doit être connecté lors de la création de contacts.

    
    </div>

7.  Dans l’onglet création d’utilisateur, vérifiez que les paramètres sont corrects. La plage d’utilisateurs pour laquelle les contacts seront créés est obtenue à partir de l’onglet Création de l’utilisateur.

8.  Cliquez sur créer des contacts pour commencer la création du contact. Ce processus peut prendre plusieurs minutes. Une fois l’opération terminée, une boîte de dialogue s’affiche avec le message « l’opération s’est déroulée correctement ». Vous pouvez valider les contacts qui ont été créés en ouvrant une session en tant qu’utilisateur créé à partir de l’onglet création d’utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Une fois les contacts créés, cet outil redémarrera tous les serveurs frontaux dans le pool cible. Le démarrage des serveurs frontaux peut prendre plus de temps (jusqu’à 2 heures), selon le nombre de contacts créés par cette opération.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Liste de distribution

L’une des fonctionnalités de l’outil stress and performance de Lync Server 2013 consiste à simuler la fonctionnalité d’extension de liste de distribution (DL) dans Lync 2013. Si vous ne souhaitez pas activer le développement de la LD dans UserProvisioningTool, vous pouvez ignorer cette étape.

![Onglet Création de liste de distribution.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Onglet Création de liste de distribution.")

L’onglet Liste de distribution vous permet de créer des listes de distribution que l’outil stress and performance utilisera pour la fonctionnalité d’extension de liste de distribution. Avant de créer des listes de distribution, Lync Server 2013 doit déjà être installé. Vous devez avoir exécuté Lync Server 2013 ForestPrep. Dans le cas contraire, les attributs DL n’existent pas dans le schéma des services de domaine Active Directory et l’outil ne pourra pas créer de listes de distribution.

Pour configurer les listes de distribution, procédez comme suit.

1.  Dans nombre de listes de distribution, spécifiez le nombre total de listes de distribution que vous souhaitez créer. (Nous vous recommandons de commencer avec deux fois le nombre d’utilisateurs). Ils sont numérotés de 0 à n-1.

2.  Dans préfixe de liste de distribution, spécifiez le préfixe que devra posséder les listes de distribution. Par exemple, si vous spécifiez 100 DL et un préfixe testDL, les listes de distribution seront nommées testDL0, testDL1, et ainsi de suite, via testDL99.

3.  Dans membres minimum d’une liste dist., spécifiez le nombre minimal d’utilisateurs à ajouter dans chaque liste de distribution.

4.  Dans nombre maximal de membres dans une liste dist., spécifiez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.

<div>

## <a name="create-distribution-lists-button"></a>Bouton créer des listes de distribution

Lorsque vous cliquez sur le bouton créer des listes de distribution, l’outil interroge les services de domaine Active Directory pour déterminer si les listes de distribution correspondant au préfixe et aux numéros existent déjà. L’outil crée uniquement ceux qui n’existent pas encore. Lorsque vous ajoutez des membres à ces listes de distribution nouvellement créées, les utilisateurs sont sélectionnés dans la plage spécifiée dans l’onglet création d’utilisateur.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Onglet Configuration du service informations d’emplacement

L’une des fonctionnalités de l’outil stress and performance de Lync Server 2013 est de générer des fichiers de configuration factices pour le service d’informations d’emplacement. En règle générale, le service informations d’emplacement n’a pas d’impact significatif sur les performances des serveurs.

![Onglet Configuration du service informations d’emplacement.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Onglet Configuration du service informations d’emplacement.")

Si vous choisissez de tester cette fonctionnalité, vous pouvez renseigner les valeurs mentionnées dans le formulaire, puis cliquer sur le bouton générer des fichiers de configuration LIS. Il génère des fichiers CSV appelés lis\_subnet. csv, lis\_switches. csv,\_lis ports. csv et lis\_WAP. csv. Vous pouvez ensuite importer ces fichiers CSV dans la base de données LIS à l’aide de la cmdlet **Set-CsLisSubnet** , de l’applet de commande Set **-CsLisSwitch** , de l’applet de commande **Set-CsLisPort** et de l’applet de commande **Set-CsWirelessAccessPoint** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

