---
title: Guide de migration et d’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Conseils pour la gestion de la transition aux équipes de Skype pour les entreprises
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16a10f73614626a422bf6b869d08c4019982d0d2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375892"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guide de migration et d’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises

En avril de 2018, Microsoft clarification de l’aide à la migration pour les équipes de Skype pour les entreprises et comment ces deux clients peuvent coexister pour un utilisateur donné. À ce stade, nous avons annoncé modifications planifiées pour simplifier la gestion et accroître la satisfaction des utilisateurs finaux. Depuis, Microsoft a développé une mise à jour pour l’expérience utilisateur d’administration, compatible avec ce plan. Les instructions de ce document reflètent ces modifications.

Comme annoncé précédemment, TeamsInteropPolicy a été retiré. Sa fonctionnalité a été consolidée dans TeamsUpgradePolicy. Interopérabilité et la migration sont gérés à l’aide du mode « coexistence » tel que déterminé par TeamsUpgradePolicy. Sélection du mode de l’utilisateur gère le routage des appels entrants et salles de conversation et si utilisateur planifie les réunions dans des équipes ou Skype pour les entreprises.  Bientôt, conjointement avec la TeamsAppPermissionsPolicy à venir, mode gère également dans le client de l’utilisateur peut lancer des conversations et les appels. 

Configuration TeamsInteropPolicy n’est plus nécessaire. Il n’est pas respecté, sauf si TeamsUpgradePolicy a mode = hérité.  Prise en charge TeamsUpgradePolicy est terminée, les clients doivent mettre à jour leur configuration pour utiliser un mode autre que hérité. Octroi des instances de TeamsUpgradePolicy avec mode = hérité est désormais bloquée par défaut.

## <a name="fundamental-concepts"></a>Concepts fondamentaux

1.  *Interopérabilité* : communication 1 à 1 entre un Lync/Skype pour l’utilisateur d’entreprise et un utilisateur d’équipes.

2.  *Fédération* : Communication entre les utilisateurs à partir de différents clients.

3.  Toutes les équipes, les utilisateurs ont un Skype sous-jacente pour le compte d’entreprise qui est « hébergé » soit en ligne ou locale :
    - Les utilisateurs utilisent déjà Skype pour Business Online utilisent leur compte en ligne existant.
    - Les utilisateurs déjà à l’aide de Skype pour Business/Lync local utilisent leur compte local existant.
    - Les utilisateurs pour lesquels nous ne pouvons pas détecter un Skype existant pour le compte professionnel aura une Skype pour Business Online compte configuré automatiquement lors de la création de l’utilisateur d’équipes. Aucun Skype pour la licence entreprise n’est requis.

4.  Si vous disposez d’un déploiement local de soit Skype pour Lync ou de l’entreprise et que vous souhaitez que ces utilisateurs à des utilisateurs des équipes, vous devez au minimum vous assurer que Azure AD Connect est en cours de synchronisation du msRTCSIP-DeploymentLocator attribut dans DAS, ainsi que les équipes/Skype pour les entreprises Online correctement détecte votre environnement local. En outre, pour déplacer des utilisateurs vers les équipes seule (autrement dit, mettre à niveau un utilisateur), *vous devez configurer Skype pour le mode hybride Business*.

5.  Interopérabilité entre équipes et Skype pour les utilisateurs professionnels n’est possible que *Si l’utilisateur équipes est hébergé en ligne dans Skype pour les entreprises*. Le Skype pour l’utilisateur d’entreprise peut être hébergé soit localement (et nécessite la configuration Skype pour un environnement hybride Business) ou en ligne. Permettent aux utilisateurs qui sont hébergés dans Skype pour Business local équipes en mode îles (défini plus loin dans ce document), mais ils ne peuvent pas permet aux équipes interop ou fédérer avec d’autres utilisateurs qui utilisent Skype pour les entreprises.  

6.  Mise à niveau d’un utilisateur aux équipes (autrement dit, leur accorder TeamsUpgradePolicy avec Mode = TeamsOnly), l’utilisateur doit être hébergé en ligne dans Skype pour les entreprises. Cette opération est obligatoire pour garantir l’interopérabilité, la fédération et l’administration complète de l’utilisateur d’équipes. Pour mettre à niveau des utilisateurs qui sont hébergés sur un système local, utilisez `Move-CsUser` à partir de l’environnement local administrateur des outils pour déplacer vers le premier l’utilisateur de Skype pour Business Online. Puis accorder TeamsUpgradePolicy et TeamsInteropPolicy à l’utilisateur en ligne ou portail moderne permet d’affecter le mode TeamsOnly. Une fois CU8 pour Skype pour navires Business Server 2015, client peut simplement utiliser la nouvelle `-MoveToTeams` basculer dans `Move-CsUser` qui combine ces 2 étapes à 1.

7.  La stratégie de base pour la gestion de la mise à niveau et interopérabilité de base est TeamsUpgradePolicy. TeamsInteropPolicy n’est plus utilisé, sauf lorsque l’utilisation du mode TeamsUpgradePolicy = hérités et les clients qui utilisent le mode = hérité doit mettre à jour leur configuration de TeamsUpgradePolicy à utiliser un autre mode.  Mode d’attribution = hérité est désormais bloquée par défaut, bien que les administrateurs peuvent remplacer à l’aide de `-Force` pour le moment. Enfin, la `-Force` commutateur sera supprimé et accorder le mode = hérité n’est pas possible. 

8.  Pour utiliser le système téléphonique d’équipes des fonctionnalités, les utilisateurs doivent être en mode TeamsOnly (autrement dit, hébergés dans Skype pour Business Online et mis à niveau vers les équipes) et ils doivent être configurés pour le système téléphonique de Microsoft [Routage Direct](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (qui vous permet d’utiliser le système téléphonique avec votre propriétaire de jonctions SIP et SBC) ou possèdent un Office 365 appelant Plan de.   

9.  Planification de réunions d’équipes à une conférence Audio (entrant ou appel sortant via PSTN) est actuellement disponible uniquement pour les utilisateurs qui sont hébergés dans Skype pour Business Online. Appuyez sur est prise en charge pour les utilisateurs d’équipes avec un Skype locale pour le compte de l’entreprise.


## <a name="coexistence-modes"></a>Modes de coexistence

Pour simplifier la gestion et accroître la satisfaction des utilisateurs finaux, interopérabilité et la migration sont maintenant gérés en fonction de « mode de coexistence » à l’aide de TeamsUpgradePolicy. Mode d’un utilisateur détermine :

- *Routage des télécopies entrantes* : dans quels ne client (équipes ou Skype pour les entreprises) entrant conversations et appelle terrain ? 
- *Planification de la réunion* : le service qui est utilisé pour la planification de réunions et en vous assurant que le complément approprié est présent dans Outlook. Notez que TeamsUpgradePolicy ne gère pas participer à une réunion. Les utilisateurs peuvent toujours *participer à* une réunion, qu’il s’agisse d’un Skype pour conférence Business ou équipes.
- *L’expérience client* : quelles sont les fonctionnalités sont disponible dans les équipes et/ou Skype pour client d’entreprise ? Ceci est implémenté pour le mode TeamsOnly. Prise en charge pour les autres modes dépend de la TeamsAppPermissionsPolicy à venir. Lorsque cette nouvelle stratégie est en place, TeamsUpgradePolicy aura une dépendance sur pour garantir que les équipes est correctement configuré pour le mode de votre choix.

Les modes planifiées sont répertoriés ci-dessous. SfBWithTeamsCollab et SfBWithTeamsCollabAndMeetings autorisera mixte d’utilisation de ces deux clients, mais aucune fonctionnalité qui se chevauchent. Mode (îles) permet l’utilisation de ces deux clients, mais avec chevauchement des fonctionnalités. Par exemple, en mode (îles), un utilisateur peut lancer une conversation dans soit Skype pour les équipes ou de l’entreprise, mais dans SfBWithTeamsCollab, ils peuvent uniquement converser dans Skype pour les entreprises. Notez que pas tous les modes sont encore totalement disponibles.  
</br>
</br>

|Mode|Comportement de routage|Planification de la réunion|Expérience du client|
|---|---|---|---|
|(Îles)|VOIP entrant appelle et conversations terrestre dans le même client en tant qu’expéditeur<sup>1</sup>|Les deux|Les utilisateurs finaux peuvent lancer des appels et les salles de conversation à partir d’un client et permet de planifier des réunions à partir d’un client.|
|SfBOnly|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Skype pour les entreprises uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations de Skype pour les entreprises et planifier uniquement Skype pour les réunions d’entreprise. (PAS ENCORE APPLIQUÉE)|
|SfBWithTeamsCollab<sup>2</sup>|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Skype pour les entreprises uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations de Skype pour les entreprises et planifier uniquement Skype pour les réunions d’entreprise. Ils peuvent également utiliser des canaux dans les équipes. (PAS ENCORE APPLIQUÉE)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Équipes uniquement|Les utilisateurs finaux peuvent passer des appels et conversations Skype pour les entreprises uniquement et uniquement à partir de planifient des réunions d’équipes. Ils peuvent également utiliser des canaux dans les équipes. (PAS ENCORE APPLIQUÉE)|
|TeamsOnly|Conversations et les appels entrants sont acheminées vers les équipes|Équipes uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations des équipes. Skype pour les entreprises est uniquement disponible pour participer à des réunions.|
|Hérité|Routage basé sur TeamsInteropPolicy|Aucun impact|Aucun impact. Il s’agissait d’un mode temporaire facilités passage de TeamsInteropPolicy à TeamsUpgradePolicy. TeamsUpgradePolicy est entièrement pris en charge les clients ne doivent pas utiliser ce mode plus et doivent mettre à jour leurs configurations aux modes de hérité. |
|||||

**Notes :**

<sup>1</sup> pour plus d’informations sur PSTN d’appel, voir tableau à la fin de ce document.

<sup>2</sup> SfBWithTeamsCollab n'est pas encore exposée dans l’expérience utilisateur d’administration, car il actuellement se comporte pas différemment en mode SfBOnly. Lorsque l’expérience du client est remis, ce mode sera disponible.

<sup>3</sup> SfBWithTeamsCollabAndMeetings n’est pas encore disponible. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy : gestion de la migration et coexistence

TeamsUpgradePolicy expose trois propriétés. Les principales propriétés sont en Mode et NotifySfbUsers. Action est un paramètre hérité et est entièrement redondante avec la combinaison de Mode et NotifySfbUsers.
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(valeur par défaut en italique)|Description|
|---|---|---|---|
|Mode|Enum|*(Îles)*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>Hérité|Indique le mode, dans que le client doit s’exécuter. Si le mode = Legacy, composants consommation de cette stratégie seront rétabli en respectant TeamsInteropPolicy. TeamsUpgradePolicy est maintenant entièrement pris en charge et les clients doivent mettre à jour leurs modes d’utilisation configurations autre que hérité.|
|NotifySfbUsers|Bool|*False* ou true|Indique s’il faut afficher une bannière dans le Skype pour client Business informant l’utilisateur que les équipes remplacera bientôt Skype pour les entreprises. Il ne peut pas être la valeur true si le Mode = TeamsOnly.|
|Action|Enum|*None*, avertir, mise à niveau|Il s’agit d’un paramètre hérité qui est finalement supprimé, car elle est redondante avec la combinaison de Mode et NotifySfbUsers. |
|||||

Les équipes fournit toutes les instances appropriées de TeamsUpgradePolicy par le biais des stratégies intégrées, en lecture seule. Par conséquent, obtenir uniquement et applets de commande Grant sont disponibles. Les instances intégrés sont répertoriés ci-dessous.
</br>
</br>

|Identity |Mode|NotifySfbUsers|Action|Commentaires|
|---|---|---|---|---|
|(Îles)|(Îles)|Faux|Aucun||
|IslandsWithNotify|(Îles)|True|Avertir||
|SfBOnly|SfBOnly|Faux|Aucun|Pour l’instant, ce mode est effectivement la même que le client par défaut du paramètre = SfB. Nous pensons à l’avenir que cela restreint la fonctionnalité d’équipes.|
|SfBOnlyWithNotify|SfBOnly|True|Avertir|Pour l’instant, ce mode est effectivement la même que le client par défaut du paramètre = SfB. Nous pensons à l’avenir que cela restreint la fonctionnalité d’équipes.|
|SfBWithTeamsCollab|SfBWithTeamsCollab|Faux|Aucun|Ce mode existe au niveau de la couche PowerShell mais n’est pas encore exposé dans l’expérience utilisateur d’administration. À partir d’un point de vue de routage, il s’agit identique au mode SfBOnly. Lorsque TeamsAppPolicy est disponible, cela n’autorisera que canaux dans l’application des équipes.|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|Avertir|Ce mode existe au niveau de la couche PowerShell mais n’est pas encore exposé dans l’expérience utilisateur d’administration. À partir d’un point de vue de routage, il s’agit identique au mode SfBOnly. Lorsque TeamsAppPolicy est disponible, cela n’autorisera que canaux dans l’application des équipes.|
|UpgradeToTeams|TeamsOnly|Faux|Mise à niveau|Utilisez ce mode pour mettre à niveau des utilisateurs aux équipes et empêcher conversation, appel et planifier des réunions dans Skype pour les entreprises.|
|Globale|Hérité|Faux|Aucun|Le mode met à jour dans un avenir proche des îles.|
|NoUpgrade|Hérité|Faux|Aucun|Cette instance sera éventuellement être retirée.|
|NotifyForTeams|Hérité|True|Avertir|Cette instance sera éventuellement être retirée.|
||||||

Ces instances de stratégie peuvent être accordées à des utilisateurs individuels ou sur un client à l’échelle. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) aux équipes, accordez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau le client entière, omettez le paramètre identity de la commande grant :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-being-retired"></a>TeamsInteropPolicy est obsolète 

Comme indiqué précédemment, TeamsInteropPolicy a été remplacée par TeamsUpgradePolicy. Tous les composants précédemment réglé TeamsInteropPolicy ont été mis à jour pour honorer TeamsUpgradePolicy au lieu de cela. 

Microsoft a déjà introduit le mode « Hérité » afin de faciliter la transition à partir de TeamsInteropPolicy vers TeamsUpgradePolicy, mode hérité dans, les composants de routage qui compris TeamsUpgradePolicy seraient revenir au TeamsInteropPolicy. Routage prend maintenant entièrement en charge TeamsUpgradePolicy et il n’est plus nécessaire d’utiliser le mode hérité. Les clients qui utilisent le mode hérité doivent mettre à jour leur configuration de TeamsUpgradePolicy d’utiliser une des autres modes. 

Les clients qui utilisent toujours en mode hérité reçoivent un rappel que seules les trois instances spécifiques de TeamsInteropPolicy répertoriées ci-dessous sont prises en charge. Dans chaque cas, la valeur de CallingDefaultClient correspond à la valeur de ChatDefaultClient et AllowEndUserClientOverride a toujours la valeur false. 
</br>
</br>
**Prise en charge des instances de TeamsInteropPolicy lors de l’utilisation du mode TeamsUpgradePolicy = hérité**
|Identity |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|Faux|Par défaut|Par défaut|
|`DisallowOverrideCallingSfbChatSfb`|Faux|SFB|SFB|
|`DisallowOverrideCallingTeamsChatTeams`|Faux|Teams|Teams|
|||||

Utilisez la syntaxe de commande suivante, où $policy est une des valeurs d’identité ci-dessus :`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>Considérations relatives à la fédération

Fédération des équipes à un autre utilisateur à l’aide de Skype entreprise requiert l’utilisateur équipes hébergés en ligne dans Skype pour les entreprises. Finalement, équipes, les utilisateurs hébergés dans Skype pour Business locale sera vous fédérer avec d’autres utilisateurs d’équipes.

TeamsUpgradePolicy gère le routage des appels et des conversations fédérées entrantes. Pour faciliter les autres organisations d’établir des communications fédérées avec les utilisateurs de votre organisation, il est recommandé de choisir un mode qui achemine spécifiquement soit à Skype pour Business ou équipes, plutôt que des îles.
</br>
|Pour acheminer les appels et conversations pour...|Accorder une instance de TeamsUpgradePolicy</br> avec un de ces modes
|---|---|
|Skype Entreprise|SfBOnly, SfBWithTeamsCollab, </br>SfBWithTeamsCollabAndMeetings|
|Teams|TeamsOnly |
|||

Lorsque les destinataires sont en mode (îles), conversations et appels à partir de la terre d’utilisateurs fédérés dans SfB.

## <a name="completing-the-transition-to-mode-management"></a>Fin de la transition vers la gestion de mode

Fin de l’année, Microsoft prévoit d’introduire un nouveau type de stratégie, TeamsAppPermissionsPolicy, afin de contrôler les portions de client d’équipes sont activées (telles que la messagerie instantanée, réunions, la conversation, les canaux). Lorsque la nouvelle stratégie pour activer/désactiver les charges de travail en équipe est disponible, TeamsUpgradePolicy seront mis à jour afin que lorsqu’un administrateur tente d’accorder une instance de TeamsUpgradePolicy à un utilisateur, elle vérifie tout d’abord pour vous assurer que TeamsAppPolicy est correctement configuré pour le mode de votre choix. Si ce n’est pas le cas, l’octroi échoue avec une erreur expliquant comment l’autre stratégie doit tout d’abord être définie. 

Jusqu'à ce que TeamsAppPolicy devient disponible, TeamsUpgradePolicy régit essentiellement le routage des appels et des salles de conversation, ainsi que la planification de réunion (comme exposé par le biais des compléments Outlook). Étant donné que le comportement du client des équipes n’est pas encore en place, pas tous les modes sont activés dans le portail moderne. À partir d’un point de vue de routage, les modes SfBOnly, SfBWithTeamsCollab et SfBWithTeamsCollabAndMeetings sont identiques. 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>Action requise pour les organisations qui ont déjà utilisé TeamsInteropPolicy

Les clients qui utilisent toujours en mode hérité procédez comme suit :

1. Assurez-vous que les utilisateurs avec TeamsInteropPolicy sont affectés à une seule de ces trois instances intégrés, pour le CallingDefaultClient = ChatDefaultClient et pour quelle AllowEndUserClientOverride = false. Ces instances sont les suivants :
   </br>
   </br>

   |Identity |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|Faux|Par défaut|Par défaut|
   |`DisallowOverrideCallingSfbChatSfb`|Faux|SFB|SFB|
   |`DisallowOverrideCallingTeamsChatTeams`|Faux|Teams|Teams|
   |||||

    Utilisez la syntaxe de commande suivante, où $policy est une des valeurs d’identité ci-dessus :

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **Microsoft demande aux clients de mettre à jour leurs stratégies par le 30 juin 2018.** Un certain temps après cela, vous souhaitez supprimer les autres instances du TeamsInteropPolicy à Microsoft.</br> 
    ***Les organisations qui ne mettent pas à jour sur une de ces instances auront finalement leurs utilisateurs mis à jour automatiquement à une de ces instances. Nous préfèrent évidemment que les clients cela, afin que vous pouvez choisir la meilleure pour vos utilisateurs.***

2. Si vous avez personnalisé la stratégie globale intégrée, annuler l’opération. Votre stratégie globale doit avoir les valeurs suivantes :
   </br>
   </br>

    |Paramètre|Valeur|
    |---|---|
    |`AllowEndUserClientOverride`|Faux|
    |`CallingDefaultClient`|Par défaut|
    |`ChatDefaultClient`|Par défaut|
    |||

    Si une des valeurs est différente de celle ci-dessus, exécutez ce qui suit pour supprimer toutes les personnalisations spécifiques au client :

    `Grant-CsTeamsInteropPolicy -PolicyName $null`

## <a name="detailed-mode-descriptions"></a>Descriptions du mode détaillé
</br>
</br>

|Mode|Explication|
|---|---|
|**(Îles)**|Un seul utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et VOIP appelle de soit Skype pour client équipes ou de l’entreprise. Remarque : Avec Skype pour les entreprises, les utilisateurs hébergés sur site ne peut pas démarrer à partir d’équipes pour atteindre une autre Skype pour l’utilisateur d’entreprise.<li>Reçoit les appels VOIP initiées dans Skype pour les entreprises par un autre utilisateur dans leur Skype pour client d’entreprise et des conversations.<li>VOIP de reçoit les appels démarrés dans les équipes par un autre utilisateur dans le client de leurs équipes.<li>Reçoit des salles de conversation initiées dans les équipes par un autre utilisateur dans :<ul><li>Skype pour les entreprises fourni le destinataire est hébergé en ligne et jamais connecté à des équipes<li>Équipes dans tous les autres cas.</ul><li>Présente la fonctionnalité PSTN comme indiqué ci-dessous :<ul><li>Si l’utilisateur est hébergé dans Skype pour Business locaux, appels PSTN sont émis et reçus dans Skype pour les entreprises.<li>Si l’utilisateur est hébergé en ligne, l’utilisateur a système téléphonique, auquel cas l’utilisateur :<ul><li>Initialisation et reçoit des appels PSTN dans les équipes si l’utilisateur est configuré pour le routage Direct<li>Initialisation et reçoit des appels PSTN dans Skype pour les entreprises si l’utilisateur a un Plan d’appel MS ou se connecte au réseau RTC via un Skype pour édition dans le nuage connecteur ou un déploiement local de Skype pour Business Server (voix hybride)</ul></ul><li>Permet de planifier des réunions dans des équipes ou Skype pour les entreprises (et s’affiche les deux plug-ins par défaut).<li>Peuvent participer à n’importe quel Skype de réunion équipes ou de l’entreprise ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un seul utilisateur exécute uniquement Skype pour les entreprises. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et appels Skype pour les entreprises uniquement.<li>Reçoit toute conversation/appel dans leur Skype pour client d’entreprise, quel que soit où initialisé, sauf si l’initiateur est un utilisateur d’équipes avec Skype pour les entreprises hébergés localement. * <li>Permet de planifier uniquement Skype pour les réunions d’entreprise, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise. </br> *Mode (îles) à l’aide avec des utilisateurs locaux n’est pas recommandé en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur d’équipes avec Skype pour les entreprises hébergés localement lance un appel ou une conversation à un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit un email.* conversation/appel manqué|
|**SfBWithTeamsCollab**|Un seul utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Comporte des fonctionnalités d’un utilisateur en mode SfBOnly.<li>Les équipes a activé uniquement pour la collaboration de groupe (chaînes) ; planification de la conversation/appel/réunion sont désactivées.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(prévu)|Un seul utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :<ul><li>A la conversation et les fonctions d’appel de l’utilisateur en mode SfBOnly.<li>Les équipes a activé pour la collaboration de groupe (chaînes) ; conversation et appel sont désactivées.<li>Permet de planifier des réunions d’équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.</ul>|
|**TeamsOnly**</br>(requiert SfB Online accueil)|Un seul utilisateur exécute uniquement les équipes. Cet utilisateur :<ul><li>Reçoit les conversations et appelle dans leur client équipes, quel que soit où initié.<li>Peuvent lancer des conversations et les appels des équipes uniquement.<li>Permet de planifier des réunions dans les équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.<li>Peut continuer à utiliser Skype pour les téléphones IP de l’entreprise.</ul> |
|**Hérité**</br>(valeur par défaut)|Ce mode a été utilisé lors de la transition TeamsInteropPolicy à TeamsUpgradePolicy pour garantir une expérience cohérente comme logiciel de modifications sont déployées. Ce mode n’est plus nécessaire à présent que la prise en charge totale de TeamsUpgradePolicy. Les clients qui utilisent le mode = hérité doit mettre à jour leur configuration sur les autres modes.|
|||




## <a name="related-topics"></a>Rubriques connexes

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[Grant-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[Remove-CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Nouvelle CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
