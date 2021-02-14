---
title: Consolidation du cloud pour Teams et Skype Entreprise
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cet article explique comment réaliser cette consolidation pour les organisations avec des déploiements locaux de Skype Entreprise (ou Lync) qui cherchent à déplacer leur charge de travail UC vers Teams et/ou Skype Entreprise Online.
ms.openlocfilehash: d2733ffacf8b56a5cfe4217553f533950eb82e36
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221488"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Regroupement dans le cloud pour Teams et Skype Entreprise

De nombreuses entreprises de grande taille ont plusieurs forêts AD locales et, dans certains cas, les clients ont plusieurs déploiements d’Exchange et/ou de Skype Entreprise Server (ou Lync Server). De plus, même les organisations disposant d’une seule forêt locale pourraient se retrouver dans une situation similaire via une fusion ou une acquisition d’entreprises. Lorsque ces clients se déplacent vers le cloud, ils souhaitent consolider les instances multiples d’une charge de travail sur site donnée dans le cloud en une seule organisation Microsoft 365 ou Office 365. Cet article explique comment réaliser cette consolidation pour les organisations avec plusieurs déploiements locaux de Skype Entreprise (ou Lync) qui souhaitent déplacer leur charge de travail UC vers le cloud Microsoft, par exemple, Microsoft Teams et/ou Skype Entreprise Online.

Historiquement, les recommandations ont été apportées aux clients dans cette situation afin de consolider d’abord les déploiements locaux, puis de passer au cloud. Bien qu’il s’agit toujours d’une option, cet article décrit une solution basée sur de nouvelles fonctionnalités qui permet aux organisations avec plusieurs déploiements Skype Entreprise de migrer un déploiement à la fois vers une seule organisation Microsoft 365 ou Office 365, sans opération de consolidation locale. Notez que même avec cette nouvelle fonctionnalité, Skype Entreprise Online et Microsoft Teams ne peuvent pas prendre en charge plusieurs forêts Skype Entreprise/Lync en mode hybride avec une seule organisation Microsoft 365 ou Office 365. 

> [!Important]
> Avant d’utiliser ce guide pour la configuration, veillez à passer en revue et à comprendre les [limitations,](#limitations)car elles peuvent affecter votre organisation.

## <a name="overview-of-cloud-consolidation"></a>Vue d’ensemble de la consolidation dans le cloud

La consolidation de tous les utilisateurs locaux dans le cloud dans une seule organisation Microsoft 365 ou Office 365 peut être réalisée pour n’importe quelle organisation avec plusieurs déploiements Skype Entreprise, à condition que les conditions clés suivantes soient remplies :

- Au maximum une organisation Microsoft 365 ou Office 365 doit être impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
- À un moment donné, une seule forêt Skype Entreprise locale peut être en mode hybride (espace d’adressage SIP partagé). Toutes les autres forêts Skype Entreprise locales doivent rester locales (et être mutuellement fédérées entre elles). Notez que ces autres  organisations locales peuvent se synchroniser avec AAD si vous le souhaitez avec de nouvelles fonctionnalités pour désactiver les domaines [SIP](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) en ligne disponibles à partir de décembre 2018.

Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement tous les utilisateurs d’une seule forêt Skype Entreprise hybride individuellement vers l’organisation Microsoft 365 ou Office 365 à l’aide de la fonctionnalité Espace d’adressare SIP partagé, puis désactiver l’hybride avec ce déploiement local, avant de migrer le déploiement skype entreprise local suivant. Avant la migration vers le cloud, les utilisateurs locaux restent dans un état fédéré avec les utilisateurs qui ne sont pas représentés dans le même annuaire local de l’utilisateur.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemple canonique de consolidation cloud

Envisagez une organisation avec deux déploiements locaux fédérés distincts de Skype Entreprise qui souhaitent les consolider en ligne dans Microsoft Teams ou Skype Entreprise Online.


|Détails de l’état d’origine |Détails de l’état souhaité |
|---------|---------|
|<ul><li>2 déploiements locaux skype entreprise indépendants dans des forêts AD distinctes<li>Une forêt au maximum est hybride avec Skype Entreprise Online <li> Les orgs sont fédérés les uns avec les autres <li>Les utilisateurs ne sont pas synchronisés entre ces forêts<li> L’organisation peut avoir une organisation Microsoft 365 ou Office 365 et synchroniser son annuaire avec Azure AD</ul>|<ul> <li>1 organisation Microsoft 365 ou Office 365<li>Plus aucun déploiement local, donc aucun déploiement hybride restant<li>Tous les utilisateurs locaux sont homed dans Skype Entreprise Online et peuvent éventuellement être des utilisateurs teams uniquement <li>Aucun encombrement local de Skype Entreprise n’importe où <li>Les utilisateurs ont toujours une authentification sur site</ul> |

![Consolidation de deux déploiements locaux fédérés distincts](../media/cloudconsolidationfig1.png)  

Les étapes de base pour passer de l’état d’origine à l’état final souhaité sont ci-dessous.  Notez que certaines organisations peuvent trouver leur point de départ quelque part au milieu de ces étapes. Voir [les autres points de départ,](#other-starting-points)plus loin dans cet article. Enfin, dans certains cas, l’ordre peut être ajusté en fonction des besoins. [Les contraintes et limitations clés sont décrites](#limitations) plus loin.

1.  Obtenez une organisation Microsoft 365 ou Office 365 si elle n’existe pas encore.
2.  Assurez-vous que tous les domaines SIP pertinents dans les deux déploiements locaux sont vérifiés dans les domaines Microsoft 365 ou Office 365.
3.  Choisissez un déploiement Skype Entreprise hybride avec Microsoft 365 ou Office 365. Dans cet exemple, nous allons utiliser OriginalCompany. <span> com.
4.  [Activez AAD Connect pour la forêt](configure-azure-ad-connect.md) qui deviendra d’abord hybride (OriginalCompany. <span> com). 
5.  Si vous souhaitez introduire Teams dans votre organisation, définissez la stratégie à l’échelle du client pour [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) sur SfBWithTeamsCollab ou l’un des autres modes SfB (SfBOnly ou SfBWithTeamsCollabAndMeetings). Ceci est essentiel pour assurer le routage des appels et des conversations des utilisateurs qui se déplacent vers Teams uniquement vers les utilisateurs qui restent sur site.
6.  Il est recommandé à ce stade (mais pas encore requis jusqu’à l’étape 11) d’activer [AAD Connect](cloud-consolidation-aad-connect.md) pour l’autre forêt (AcquiredCompany. <span> com). En supposant qu’AAD Connect est activé dans les deux forêts, l’organisation ressemble à la **[figure A,](#figure-a)** qui peut être un point de départ commun pour certaines organisation. 
7.  Pour tous les domaines SIP hébergés par d’autres déploiements locaux (dans ce cas, AcquiredCompany. <span> com), [désactivez ces domaines SIP dans Skype Entreprise Online](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) à l’aide de `Disable-CsOnlineSipDomain` PowerShell. (Il s’agit d’une nouvelle fonctionnalité à partir de décembre 2018.)
8.  [Configurez Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md) pour OriginalCompany. <span> com (le seul déploiement qui a encore activé les domaines SIP en ligne).
9.  Dans le déploiement hybride (OriginalCompany. <span> com), commencez à déplacer les [utilisateurs](move-users-between-on-premises-and-cloud.md) de Skype Entreprise en local vers le cloud (teams uniquement ou non) afin que ce compte soit homed dans Skype Entreprise Online. L’organisation ressemble maintenant à **[la figure B.](#figure-b)** Les principales modifications apportées à la figure A sont :
    - Les utilisateurs des deux répertoires locaux sont désormais dans AAD.
    - AcquiredCompany. <span> com est un domaine SIP en ligne désactivé.
    - Certains utilisateurs ont été déplacés en ligne vers Skype Entreprise Online ou Teams. (Voir l’utilisateur violet A.)
10. Une fois que tous les utilisateurs sont déplacés vers le cloud, désactivez l’hybride avec le déploiement local de [Skype](cloud-consolidation-disabling-hybrid.md) Entreprise pour OriginalCompany. <span> com à partir d’Office 365 :  
    - Désactivez le domaine fractioné dans l’organisation Microsoft 365 ou Office 365.
    - Désactivez la possibilité de communiquer avec Microsoft 365 ou Office 365 dans OriginalCompany. <span> com en local.
    - Mettez à jour les enregistrements DNS pour OriginalCompany. <span> com pour pointer vers Microsoft 365 ou Office 365.
11. Si ce n’est pas déjà fait, [activez AAD Connect](cloud-consolidation-aad-connect.md) pour la forêt suivante qui sera hybride (AcquiredCompany. <span> com). À ce stade, l’organisation ressemble **[à la figure C.](#figure-c)** Cela peut être un autre point de départ courant pour certaines organisations. 
12. Dans PowerShell, [activez les](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain) domaines SIP pour le déploiement local suivant qui sera hybride, AcquiredCompany. <span> com. Cette fonctionnalité est effectuée `Enable-CsOnlineSipDomain` à l’aide de la nouvelle fonctionnalité disponible à partir de décembre 2018.
13. Si vous utilisez la fédération fermée, vous devez ajouter des domaines SIP (à l’exception de .microsoftonline.com) du client en ligne pur en tant que domaines autorisés dans les mêmes \* Microsoft 365 ou Office 365.  Notez qu’il peut prendre un certain temps avant que la modification prenne effet et qu’il n’y a aucun risque à le faire tôt, c’est pourquoi nous vous suggérons de le faire bien avant de passer à l’étape 14.
14. Mettez à jour l’environnement local pour accepter tous les domaines SIP du client en ligne, afin qu’ils correspondent.
    - Mettez à jour le SAN dans tous les [certificats Edge](cloud-consolidation-edge-certificates.md) pour qu’il soit identique à la valeur précédente, ainsi que les valeurs pour les domaines SIP en ligne existants (à l’exception de *.microsoftonline.com), dans ce cas, Sip.OriginalCompany. <span> com.
    - Assurez-vous qu’OriginalCompany. <span> com est [un domaine autorisé](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) dans le déploiement local, AcquiredCompany. Ajoutez des domaines autorisés.
15. [Activez Skype Entreprise hybride](configure-federation-with-skype-for-business-online.md) entre acquiredCompany local. <span> com et le cloud.
16. Comme vous le souhaitez, [migrez les utilisateurs de l’local vers le cloud.](move-users-between-on-premises-and-cloud.md) Vous pouvez migrer les utilisateurs directement vers le mode [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) ou les migrer d’abord vers Skype Entreprise Online. Pendant cet état, l’organisation ressemble à **[la figure D](#figure-d)**.
17. Une fois tous les utilisateurs [migrés,](cloud-consolidation-disabling-hybrid.md) désactivez l’environnement hybride avec l’environnement local pour que l’organisation *soit purement cloud*!

Les diagrammes ci-dessous illustrent la configuration à différents points clés au cours de ce processus.

##### <a name="figure-a"></a>Figure A :

- Les deux organisations sont synchronisées via AAD Connect, de sorte qu’AAD dispose désormais de tous les utilisateurs des deux déploiements locaux.
- Tous les utilisateurs sont locaux.  
- Skype Entreprise hybride *n’est pas* encore configuré.
- Si les utilisateurs de l’un ou l’autre déploiement utilisent Teams, ils ne pourront pas se fédérer les uns avec les autres (ni avec n’importe quelle organisation), et ils n’auront pas non plus d’interopérabilité avec les utilisateurs de Skype Entreprise. Pendant cette phase, Microsoft recommande d’utiliser Teams uniquement pour les canaux.<br><br>
    ![Diagramme de la figure A](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figure B :

- AcquiredCompany. <span> com est un [domaine](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) SIP en ligne désactivé. Tous les utilisateurs sont locaux. S’ils utilisent Teams, ils n’ont pas de fédération ou d’interopérabilité. Pendant cette phase, Microsoft recommande d’utiliser Teams uniquement pour les canaux.
- Skype Entreprise hybride a été activé pour l’une des organisations locales.
- Certains utilisateurs de l’organisation hybride ont été déplacés vers le cloud (utilisateur A comme indiqué par l’ombrage violet). Ces utilisateurs peuvent être des utilisateurs de Skype Entreprise Online ou des utilisateurs Teams uniquement avec une interopérabilité totale et une prise en charge de la fédération.<br><br>
    ![Diagramme de la figure B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figure C :

- Tous les utilisateurs d’OriginalCompany. <span> com sont désormais dans le cloud (dans Skype Entreprise Online). Il est recommandé qu’il s’agit également de Teams uniquement.
- Configuration hybride Skype Entreprise avec OriginalCompany. <span> le déploiement com a été désactivé. Le déploiement local a disparu.
- Si AcquiredCompany. <span> com n’a pas été précédemment synchronisé avec AAD, pour continuer à partir d’ici, il doit être synchronisé maintenant. Toutefois, il n’est pas encore hybride (espace d’adressan SIP partagé) et tant que l’organisation n’est pas prête à passer à l’hybridation, le domaine SIP en ligne de l’organisation purement sur site (AcquiredCompany.com) doit rester désactivé, afin que les utilisateurs de Teams en ligne peuvent communiquer avec les utilisateurs locaux.<br><br>
    ![Diagramme de la figure C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figure D :

- AcquiredCompany. <span> com est désormais activé en tant que domaine SIP en ligne.
- La version sur site est mise à jour pour accepter OriginalCompany. <span> com. (Les certificats de domaine autorisé et de périphérie sont mis à jour).
- L’espace d’adressare SIP partagé est activé entre AcquiredCompany. <span> com et l’organisation Microsoft 365 ou Office 365.
- Certains utilisateurs de l’organisation hybride ont peut-être été déplacés vers le cloud, par exemple l’utilisateur D ci-dessous (indiqué par une ombre en violet).<br><br>
    ![Diagramme de la figure D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Autres points de départ

Les étapes de l’exemple canonique ci-dessus supposent que l’organisation commence par deux déploiements locaux fédérés sans présence de Microsoft ou d’Office 365. Toutefois, certaines organisations peuvent avoir une empreinte Microsoft 365 ou Office 365 existante, et il peut y avoir différents points d’entrée dans l’ordre ci-dessus. Il existe quatre configurations classiques :

- Plusieurs organisations locales fédérées sans organisation Microsoft 365 ou Office 365. Dans ce cas, commencez à l’étape 1.
- Plusieurs organisations locales fédérées qui synchronisent déjà plusieurs forêts Skype Entreprise en un seul client Azure AD. Une telle organisation ressemble à l’organisation hypothétique de la figure A, qui a effectué les étapes 1 à 6 et doit commencer à l’étape 7.
- Une organisation hybride qui se fédéré avec une ou plusieurs autres organisations purement locales, dont aucune n’est synchronisée avec AAD. Une telle organisation ressemblerait à l’organisation hypothétique dans **la figure E**, présentée ci-dessous.
    - Cette organisation est similaire à la figure B, qui a effectué les étapes 1 à 9, sauf :
        - Ses déploiements Skype Entreprise non hybrides ne sont *PAS* encore synchronisés avec Azure AD.
        -  Les domaines SIP en ligne ne sont pas encore désactivés. 
    - Ces organisations doivent :
        - Terminez la migration de l’organisation hybride existante et entrez la séquence ci-dessus à l’étape 10.  OR,
        - Si vous souhaitez synchroniser d’autres forêts Skype Entreprise avec AAD avant de terminer la migration de l’organisation hybride, l’organisation doit effectuer l’étape 7 (désactiver tous les domaines SIP en ligne dans tout autre déploiement Skype Entreprise local qui sera synchronisé avec AAD), puis activer AAD Connect, puis passer à l’étape 10 (désaffecter le déploiement hybride d’origine).       
                **Figure E**<br>
                ![Diagramme de la figure E](../media/cloudconsolidationfige.png)
- Une organisation Skype Entreprise Online pure (qui peut ou non utiliser Teams) qui se fédéré avec une organisation Skype Entreprise sur site distincte. Une fois que cette organisation a désactivé le domaine SIP en ligne pour l’organisation sur site et activé AAD Connect pour l’organisation Skype Entreprise sur site, elle ressemble à l’organisation hypothétique présentée dans la **[figure C](#figure-c)** qui a effectué les étapes 1 à 11.

## <a name="limitations"></a>Limites

- Au maximum une organisation Microsoft 365 ou Office 365 doit être impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
- Une seule forêt Skype Entreprise sur site peut être en mode hybride (espace d’adressa ment SIP partagé) à la fois. Toutes les autres forêts Skype Entreprise sur site doivent rester exclusivement en local et être fédérées les unes avec les autres et avec l’organisation Microsoft 365 ou Office 365.
- Avant d’être migré vers le cloud, il existe une expérience asymétrique pour les utilisateurs dans ce déploiement, car tous les utilisateurs en ligne ne sont pas représentés en local :
    - L’expérience peut être résumée comme suit :
        - Tous les utilisateurs en ligne interagissent avec les utilisateurs locaux dans l’environnement hybride comme s’il s’agit d’un utilisateur hybride.
        - Les utilisateurs locaux dans le déploiement hybride interagissent avec les utilisateurs en ligne qui sont représentés dans leur annuaire local comme s’ils étaient hybrides. 
        - Les utilisateurs locaux dans le déploiement hybride interagissent avec les utilisateurs en ligne qui ne sont pas représentés dans AD local comme fédérés.
    - Dans **[la figure D](#figure-d)** ci-dessus, l’utilisateur E est en local dans AcquiredCompany. <span> com.  L’utilisateur E interagira avec l’utilisateur D (en ligne) à l’aide de l’expérience hybride standard, mais l’utilisateur E aura une expérience fédérée avec les utilisateurs A, B et C, car ils ne sont pas représentés dans l’annuaire local. Toutefois, les utilisateurs A, B et C interagissent avec l’utilisateur E comme si l’utilisateur était en mode hybride.
    - Implications de l’interaction entre la fédération hybride et la fédération :
        - La présence n’est pas abonnée automatiquement pour les utilisateurs fédérés, sauf si l’utilisateur est marqué comme contact.
        - Le forwarding d’appel ne fonctionne pas entre les domaines fédérés.
        - Les scénarios de transfert d’appel sont plus limités.
        - La limitation peut être appliquée au trafic fédéré.
- Étant donné cette expérience asymétrique, la prise en charge officielle de la fonctionnalité d’appel dans les scénarios entre un utilisateur local et un utilisateur cloud qui ne se trouve pas dans l’annuaire local est limitée à pair à pair uniquement. 
    - Le transfert d’appel, le transfert, les files d’attente d’appels, etc. entre ces utilisateurs ne sont pas pris en charge.
    - Ces scénarios d’appels non pris en charge apparaissent toujours activés, mais dans de nombreux cas, ils échouent de manière imprévisible. 
    - Dans **[la figure D](#figure-d)** ci-dessus, l’utilisateur E est en local et les appels avec les utilisateurs A, B ou C sont pris en charge uniquement en tant qu’homologues. (Les appels avec l’utilisateur D n’auraient pas de limitations de prise en charge.)  Toutefois, une fois que l’utilisateur local E est déplacé vers le cloud, cette restriction ne s’applique plus.
- Si vous disposez de plusieurs déploiements de Skype Entreprise Server 2019 dans votre environnement, seul un de ces déploiements peut être configuré pour utiliser la Standard automatique organisationnelle, car cette fonctionnalité nécessite la configuration hybride de Skype Entreprise Server. 
- L’ordre de certaines des étapes précédentes peut être ajusté. La condition clé qui doit être remplie est que si toutes ces conditions sont remplies :
    - Plusieurs forêts Skype Entreprise sur site synchronisées avec un seul client AAD
    - Le domaine fractioné est activé avec une forêt sur site
    - Au moins un utilisateur de l’organisation hybride a été migré vers le cloud<br>   Ensuite, vous *devez désactiver* tous les autres domaines SIP en ligne de toute autre forêt Skype Entreprise sur site. Dans le cas contraire, la fédération entre les utilisateurs en ligne de l’organisation hybride et les utilisateurs locaux dans d’autres organisations se décompose dans un sens.

## <a name="implications"></a>Implications

- Étant donné que la prise en charge des fonctionnalités d’appel avancées est limitée, comme décrit ci-dessus, les organisations doivent traiter ces états asymétriques comme transitorys dans le cadre de la migration et ne pas les poursuivre en tant qu’état **stable.**  
- Les organisations avec plusieurs déploiements Skype Entreprise locaux doivent généralement commencer par un déploiement qui peut être entièrement migré vers le cloud, afin que la consolidation puisse continuer. Il est entendu que, dans certains cas, il y aura des attentes de certains groupes d’utilisateurs pour lesquels il n’est pas encore viable de passer à Teams. Lorsqu’il s’agit d’une considération dans les scénarios impliquant plusieurs forêts Skype Entreprise, commencez la migration avec une autre forêt qui n’a pas ces limitations, si possible.
- Lors du passage de l’local au cloud, les utilisateurs qui ont des relations de délégation et/ou qui sont généralement impliqués dans des scénarios de forwarding d’appel doivent être déplacés ensemble.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considérations pour le passage au mode TeamsOnly

Lorsque vous déplacez des utilisateurs de l’environnement local vers le cloud dans un environnement hybride, vous pouvez les déplacer en mode Skype Entreprise uniquement ou TeamsOnly. *Si vous prévoyez de déplacer des utilisateurs vers le mode TeamsOnly, veillez à lire d’abord cette section.*

- Lorsque vous affectez le mode TeamsOnly à un utilisateur, toutes les conversations et appels de n’importe quel autre utilisateur sont retéléélés dans le client Teams de cet utilisateur. 
- Si les utilisateurs de Skype Entreprise en local utilisent principalement le client Skype Entreprise et non Teams, envisagez de définir TeamsUpgradePolicy afin que le routage vers ces utilisateurs locaux arrive toujours dans Skype Entreprise au lieu de Teams. Pour assurer un routage correct des conversations et des appels entre les utilisateurs qui sont TeamsOnly et les utilisateurs qui utilisent toujours Skype Entreprise en local, les utilisateurs locaux doivent avoir une valeur effective de TeamsUpgradePolicy avec l’un des modes SfB, plutôt que des îles (qui est la valeur par défaut). 
    - Pour ce faire, vous devez d’abord définir l’instance globale de teamsUpgradePolicy de votre client sur *l’une des valeurs ci-après*:
        - SfBWithTeamsCollab (recommandé)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Vous pouvez accorder une stratégie à l’échelle du client à l’aide de cette commande :<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Remarque : vous devez le faire à l’échelle du client, car la stratégie ne peut pas être affectée à des utilisateurs individuels qui n’ont pas d’adresse SIP dans l’annuaire en ligne. Bien que vous avez désactivé les domaines SIP en ligne pour vos déploiements purement locaux, les utilisateurs de ces domaines n’auront pas d’adresses SIP dans l’annuaire en ligne par conception. Par conséquent, la seule façon d’appliquer la stratégie à ces utilisateurs locaux est d’affecter au niveau du client. En revanche, dans le déploiement hybride, les utilisateurs auront une adresse SIP dans l’annuaire en ligne afin de pouvoir être explicitement affectés à une stratégie s’il est souhaité qu’ils ont une valeur différente de la stratégie globale du client.
- L’expérience UX du client Teams n’honore pas encore les modes SfB de TeamsUpgradePolicy. Par exemple, dans ces modes, l’initiation d’appel et de conversation dans Teams est actuellement possible, bien qu’à l’avenir cela ne soit pas le cas. Cela peut semer la confusion chez les utilisateurs, car les réponses peuvent parfois se trouver dans Teams et parfois dans Skype Entreprise, selon les circonstances. Il est recommandé de désactiver séparément l’appel et la conversation via TeamsMessagingPolicy et TeamsCallingPolicy pour les utilisateurs qui sont toujours sur site.

## <a name="see-also"></a>Voir aussi

[Mettre à jour le certificat de serveur Edge](cloud-consolidation-edge-certificates.md)

[Mettre à jour AAD Connect pour inclure plusieurs forêts](cloud-consolidation-aad-connect.md)

[Désactiver le mode hybride pour terminer la migration vers le cloud](cloud-consolidation-disabling-hybrid.md)
