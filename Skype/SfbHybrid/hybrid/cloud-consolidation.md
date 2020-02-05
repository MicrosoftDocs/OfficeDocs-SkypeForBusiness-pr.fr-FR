---
title: Consolidation du Cloud pour teams et Skype entreprise
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
description: Cet article explique comment réaliser cette consolidation pour les organisations avec des déploiements locaux de Skype entreprise (ou Lync) qui cherchent à déplacer leur charge de travail de communications unifiées vers teams et/ou Skype entreprise online.
ms.openlocfilehash: 7f3ad27404ec80e0592baa7174b01363f1aa0ed1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726954"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Regroupement dans le cloud pour Teams et Skype Entreprise

De nombreuses entreprises de grande taille ont plusieurs forêts AD locales et, dans certains cas, les clients ont plusieurs déploiements d’Exchange et/ou de Skype Entreprise Server (ou Lync Server). De plus, même les organisations disposant d’une seule forêt locale pourraient se retrouver dans une situation similaire via une fusion ou une acquisition d’entreprises. Au fur et à mesure que ces clients migrent vers le cloud, ils souhaitent consolider les multiples instances d’une charge de travail locale donnée dans le cloud en un seul client Office 365. Cet article explique comment réaliser cette consolidation pour les organisations avec plusieurs déploiements locaux de Skype entreprise (ou Lync) qui souhaitent déplacer leur charge de travail de communications unifiées vers le Cloud Microsoft, par exemple, Microsoft teams et/ou Skype entreprise online.

Historiquement, les recommandations ont été apportées aux clients dans cette situation afin de consolider d’abord les déploiements locaux, puis de passer au cloud. Bien qu’il s’agit toujours d’une option, cet article décrit une solution basée sur de nouvelles fonctionnalités qui permet aux organisations avec plusieurs déploiements Skype entreprise de migrer un déploiement à la fois dans un seul client Office 365, sans effectuer de migration sur site. consolidé. Notez que même avec cette nouvelle fonctionnalité, Skype entreprise Online et Microsoft Teams ne prennent pas en charge plusieurs forêts Skype entreprise/Lync en mode hybride avec un seul client Office 365. 

> [!Important]
> Avant d’utiliser ce guide pour la configuration, veillez à examiner et à comprendre les [limites](#limitations), car elles peuvent affecter votre organisation.

## <a name="overview-of-cloud-consolidation"></a>Vue d’ensemble de la consolidation dans le cloud

La consolidation de tous les utilisateurs en local dans le cloud en un seul client Office 365 peut être obtenue pour les organisations ayant plusieurs déploiements de Skype Entreprise, pour autant que les exigences clés suivantes soient remplies :

- Un seul client Office 365 au maximum doit être impliqué. La consolidation dans des scénarios comportant plusieurs clients Office 365 n’est pas prise en charge.
- À un moment donné, une seule forêt Skype Entreprise locale peut être en mode hybride (espace d’adressage SIP partagé). Toutes les autres forêts Skype Entreprise locales doivent rester locales (et être mutuellement fédérées entre elles). Notez que ces autres organisations locales *peuvent* effectuer une synchronisation avec AAD si vous le souhaitez avec de [nouvelles fonctionnalités pour désactiver les domaines SIP en ligne](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) disponibles à partir du 2018 décembre.

Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement tous les utilisateurs d’une seule forêt Skype Entreprise hybride séparément vers le client Office 365 à l’aide de la fonctionnalité d’espace d’adressage SIP partagé, puis désactiver l’environnement hybride avec ce déploiement local, avant de passer à la migration du déploiement Skype Entreprise suivant. Avant la migration vers le cloud, les utilisateurs locaux restent dans un état fédéré avec les utilisateurs qui ne sont pas représentés dans le même annuaire local de l’utilisateur.  

## <a name="canonical-example-of-cloud-consolidation"></a>Exemple de consolidation de Cloud canonique

Imaginez une organisation disposant de deux déploiements distincts sur site de Skype entreprise qui souhaitent les consolider en ligne dans Microsoft teams ou Skype entreprise online.


|Détails de l’état d’origine |Détails de l’état souhaité |
|---------|---------|
|<ul><li>2 déploiements indépendants de Skype entreprise sur site dans des forêts AD distinctes<li>1 la forêt est en partie hybride avec Skype entreprise Online <li> Les développées sont fédérés les uns avec les autres <li>Les utilisateurs ne sont pas synchronisés entre ces forêts<li> L’organisation peut disposer d’un client Office 365 et être en synchronisation avec Azure AD</ul>|<ul> <li>1 client Office 365<li>Aucun déploiement local n’étant plus disponible, il n’y a pas de sites hybrides restants.<li>Tous les utilisateurs de l’organisation locale sont hébergés dans Skype entreprise Online et peuvent éventuellement être des utilisateurs de teams uniquement <li>Aucune empreinte locale de Skype entreprise Anywhere <li>Les utilisateurs ont toujours une authentification locale</ul> |

![Consolidation de deux déploiements locaux fédérés distincts](../media/cloudconsolidationfig1.png)  

Les étapes de base pour obtenir de l’état d’origine vers l’état final souhaité sont indiquées ci-dessous.  Notez que certaines organisations peuvent trouver que leur point de départ se situe au milieu de ces étapes. Voir [les autres points de départ](#other-starting-points), plus loin dans cet article. Enfin, dans certains cas, l’ordre peut être ajusté en fonction des besoins. Les [contraintes et limitations de clés](#limitations) sont décrites plus loin.

1.  Obtenir un client Office 365 s’il n’en existe pas encore.
2.  Assurez-vous que tous les domaines SIP pertinents dans les déploiements locaux sont vérifiés pour les domaines Office 365.
3.  Sélectionnez un déploiement Skype entreprise hybride avec Office 365. Dans cet exemple, nous allons utiliser OriginalCompany. <span>com.
4.  [Activez la connexion AAD pour la forêt](configure-azure-ad-connect.md) qui va devenir hybride (OriginalCompany.<span> com). 
5.  Si vous allez introduire teams dans votre organisation, définissez la stratégie à l’échelle du client pour [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) sur SfBWithTeamsCollab ou l’un des autres modes SfB (SfBOnly ou SfBWithTeamsCollabAndMeetings). Ceci est essentiel pour garantir le routage des appels et des conversations des utilisateurs qui se déplacent vers teams uniquement aux utilisateurs qui restent sur site.
6.  À ce stade, il est recommandé (mais pas encore requis jusqu’à l’étape 11) d' [activer la connexion AAD pour l’autre forêt](cloud-consolidation-aad-connect.md) (AcquiredCompany.<span> com). En supposant que la connexion AAD est activée dans les deux forêts, l’organisation org ressemble à la **[figure A](#figure-a)**, qui peut être un point de départ commun pour certains développées. 
7.  Pour tous les domaines SIP hébergés par d’autres déploiements sur site (dans ce cas,<span> AcquiredCompany. com), [désactivez ces domaines SIP dans Skype entreprise Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) à l’aide `Disable-CsOnlineSipDomain` de PowerShell. (Il s’agit d’une nouvelle fonctionnalité de décembre 2018.)
8.  [Configurez Skype entreprise hybride](configure-federation-with-skype-for-business-online.md) pour OriginalCompany. <span>com (un déploiement qui a encore activé les domaines SIP en ligne).
9.  Dans le déploiement hybride (OriginalCompany.<span> com), commencez par [déplacer les utilisateurs de Skype entreprise sur site vers le Cloud](move-users-between-on-premises-and-cloud.md) (uniquement teams ou non) afin que ce compte soit hébergé dans Skype entreprise online. À présent, l’organisation ressemble à la **[figure B](#figure-b)**. Les principales modifications apportées à la figure A sont les suivantes :
    - Les utilisateurs des annuaires locaux se trouvent désormais dans AAD.
    - AcquiredCompany. <span>com est un domaine SIP en ligne désactivé.
    - Certains utilisateurs ont été déplacés en ligne vers Skype entreprise Online ou Teams. (Voir l’utilisateur violet A.)
10. Une fois que tous les utilisateurs sont déplacés vers le Cloud, [désactivez hybride avec le déploiement local de Skype entreprise](cloud-consolidation-disabling-hybrid.md) pour OriginalCompany. <span>com à partir d’Office 365 :  
    - Désactiver le domaine divisé dans le client Office 365.
    - Désactivez la possibilité de communiquer avec Office 365 dans OriginalCompany. <span>com en local.
    - Mettez à jour les enregistrements DNS pour OriginalCompany. <span>com pour pointer vers Office 365.
11. Si ce n’est pas déjà fait, [activez AAD Connect pour la prochaine forêt](cloud-consolidation-aad-connect.md) qui va devenir hybride<span> (AcquiredCompany. com). À ce stade, l’organisation ressemble à la **[figure C](#figure-c)**. Il peut s’agir d’un autre point de départ commun pour certaines organisations. 
12. Dans PowerShell, [activez les domaines SIP pour le prochain déploiement local](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) qui sera basé sur hybride, AcquiredCompany. <span>com. Cette opération est réalisée `Enable-CsOnlineSipDomain`à l’aide de, qui est une nouvelle fonctionnalité disponible depuis décembre 2018.
13. Si vous utilisez la Fédération fermée, vous devez ajouter tous les domaines SIP (sauf *. microsoftonline.com) du client en ligne pur en tant que domaines autorisés dans le **même** Office 365. Notez que l’opération peut prendre un certain temps avant que la modification ne prenne effet et qu’il n’y a aucun dommage à ce stade tôt, donc nous vous suggérons de le faire bien avant de passer à l’étape 14.
14. Mettez à jour l’environnement local pour qu’il accepte tous les domaines SIP du client en ligne, afin qu’ils correspondent.
    - [Mettez à jour le San dans tous les certificats de périphérie](cloud-consolidation-edge-certificates.md) de sorte qu’ils aient la même valeur qu’auparavant, ainsi que les valeurs de tous les domaines SIP en ligne existants (sauf *. microsoftonline.com), dans ce cas, SIP. OriginalCompany. <span>com.
    - Assurez-vous que OriginalCompany. <span>com est un [domaine autorisé](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) dans le déploiement local, AcquiredCompany. Ajoutez des domaines autorisés.
15. [Activer Skype entreprise hybride](configure-federation-with-skype-for-business-online.md) entre AcquiredCompany local. <span>com et le Cloud.
16. Selon vos besoins, [migrez les utilisateurs de l’organisation locale vers le Cloud](move-users-between-on-premises-and-cloud.md). Vous pouvez migrer les utilisateurs directement vers le mode [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) ou les migrer d’abord vers Skype entreprise online. Dans cet État, l’organisation ressemble à la **[figure D](#figure-d)**.
17. Une fois tous les utilisateurs migrés, [désactivez hybride avec l’environnement local](cloud-consolidation-disabling-hybrid.md) pour *faire de l’organisation un nuage pur*.

Les diagrammes ci-dessous illustrent la configuration à différents points clés pendant ce processus.

##### <a name="figure-a"></a>Figure A :

- Les deux organisations synchronisées via AAD Connect, de sorte que AAD dispose désormais de tous les utilisateurs des déploiements locaux.
- Tous les utilisateurs hébergés sur site.  
- Skype entreprise hybride n’est *pas* encore configuré.
- Si les utilisateurs dans le déploiement utilisent Teams, ils ne pourront pas se fédérer les uns avec les autres (ou une organisation), et ils ne pourront pas être interopérables avec les utilisateurs de Skype entreprise. Lors de cette étape, Microsoft recommande d’utiliser teams uniquement pour les canaux.<br><br>
    ![Illustration d’un diagramme](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>Figure B :

- AcquiredCompany. <span>com est un domaine SIP en ligne [désactivé](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) . Tous les utilisateurs sont en local. S’ils utilisent Teams, ils n’ont pas de Fédération ou d’interopérabilité. Lors de cette étape, Microsoft recommande d’utiliser teams uniquement pour les canaux.
- Skype entreprise hybride a été activé pour l’une des organisations locales.
- Certains utilisateurs de l’organisation hybride ont été déplacés vers le Cloud (utilisateur A comme indiqué par l’ombrage violet). Ces utilisateurs peuvent être des utilisateurs de Skype entreprise Online ou des utilisateurs de teams uniquement avec une prise en charge complète de l’interopérabilité et de la Fédération.<br><br>
    ![Diagramme de la figure B](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>Figure C :

- Tous les utilisateurs de OriginalCompany. <span>com sont désormais dans le Cloud (hébergé dans Skype entreprise Online). Il est recommandé de n’utiliser que des équipes.
- Configuration hybride Skype entreprise avec le OriginalCompany. <span>le déploiement com a été désactivé. Le déploiement local a disparu.
- Si AcquiredCompany. <span>com n’a pas encore été synchronisé avec AAD, pour continuer à partir de là, il doit être synchronisé maintenant. Mais il n’est pas encore hybride (espace d’adressage SIP partagé) et jusqu’à ce que l’organisation soit prête à passer à l’environnement hybride, le domaine SIP en ligne pour l’organisation locale sur site (AcquiredCompany.com) doit rester désactivé afin que les utilisateurs de teams en ligne puissent communiquer avec utilisateurs locaux.<br><br>
    ![Diagramme de la figure C](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>Figure D :

- AcquiredCompany. <span>com est désormais activé en tant que domaine SIP en ligne.
- La version locale est mise à jour pour accepter OriginalCompany. <span>com. (Le domaine autorisé et les certificats de périphérie sont mis à jour).
- L’espace d’adressage SIP partagé est activé entre AcquiredCompany. <span>com et Office 365 client.
- Certains utilisateurs de l’organisation hybride ont peut-être été déplacés vers le Cloud, comme l’utilisateur D ci-dessous (indiqué par un ombrage violet).<br><br>
    ![Diagramme de la figure D](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>Autres points de départ

Les étapes indiquées dans l’exemple canonique ci-dessus supposent que l’organisation commence par deux déploiements fédérés sur site sans présence d’Office 365. Toutefois, certaines organisations peuvent avoir une empreinte Office 365 existante et il peut y avoir des points d’entrée différents dans la séquence ci-dessus. Il existe quatre configurations typiques :

- Plusieurs organisations fédérées locales sans client Office 365. Dans ce cas, commencez à l’étape 1.
- Plusieurs organisations fédérées sur site qui synchronisent déjà plusieurs forêts Skype entreprise en un seul client Azure AD. Une telle organisation ressemble à l’organisation hypothétique de la figure A, qui a terminé les étapes 1-6 et doit commencer à l’étape 7.
- Une organisation hybride qui se fédérer avec 1 ou plusieurs organisations locales pures, aucune n’étant synchronisée avec AAD. Une telle organisation ressemblerait à l’organisation hypothétique de la **figure E**, comme indiqué ci-dessous.
    - Cette organisation est similaire à la figure B, qui a terminé les étapes 1-9, à l’exception des suivantes :
        - Ses déploiements Skype entreprise non hybrides ne sont *pas* encore en synchronisation avec Azure ad.
        -  Les domaines SIP en ligne ne sont pas encore désactivés. 
    - Ces organisations doivent :
        - Terminez la migration de l’organisation hybride existante et entrez la séquence ci-dessus à l’étape 10.  DES
        - S’il est nécessaire de synchroniser d’autres forêts Skype entreprise dans AAD avant de terminer la migration de l’organisation hybride, l’organisation doit effectuer l’étape 7 (désactiver tous les domaines SIP en ligne dans tout autre déploiement Skype entreprise local qui sera synchroniser dans AAD), puis activez AAD Connect, puis passez à l’étape 10 (mettre hors service le déploiement hybride d’origine).       
                **Figure E**<br>
                ![Diagramme de figure E](../media/cloudconsolidationfige.png)
- Une organisation Skype entreprise Online pure (qui peut ou non utiliser Teams) qui se fédérer avec une organisation Skype entreprise locale distincte. Une fois que cette organisation a désactivé le domaine SIP en ligne pour l’organisation locale et activé la connexion AAD pour l’organisation Skype entreprise locale, elle ressemble à l’organisation hypothétique illustrée dans la **[figure C](#figure-c)** qui a terminé les étapes 1-11.

## <a name="limitations"></a>Limites

- Un seul client Office 365 au maximum doit être impliqué. La consolidation dans des scénarios comportant plusieurs clients Office 365 n’est pas prise en charge.
- Une seule forêt Skype entreprise locale peut être en mode hybride (espace d’adressage SIP partagé) à la fois. Toutes les autres forêts Skype entreprise locales doivent rester entièrement locales et être fédérées les unes avec les autres et le client Office 365.
- Avant d’être migrés vers le Cloud, il existe une expérience asymétrique pour les utilisateurs dans ce déploiement, car tous les utilisateurs de la version en ligne ne sont pas représentés localement :
    - L’expérience peut être additionnée comme suit :
        - Tout utilisateur hébergé en ligne interagit avec les utilisateurs locaux dans l’environnement hybride comme s’il s’agissait d’un utilisateur hybride.
        - Les utilisateurs locaux dans le déploiement hybride interagissent avec les utilisateurs en ligne représentés dans leur annuaire local comme s’ils étaient hybrides. 
        - Les utilisateurs locaux dans le déploiement hybride interagissent avec les utilisateurs en ligne qui ne sont pas représentés dans une annonce locale comme fédéré.
    - Dans la **[figure D](#figure-d)** ci-dessus, l’utilisateur E est en local dans AcquiredCompany. <span>com.  L’utilisateur E interagit avec l’utilisateur D (hébergé en ligne) à l’aide de l’expérience hybride standard, mais l’utilisateur E dispose d’une expérience fédérée avec les utilisateurs A, B et C, car ils ne sont pas représentés dans le répertoire local. Toutefois, les utilisateurs A, B et C interagissent avec l’utilisateur E comme si l’utilisateur était en environnement hybride.
    - Implications de l’interaction hybride par rapport à la Fédération :
        - La présence n’est pas automatiquement abonnée aux utilisateurs fédérés, sauf si l’utilisateur est marqué comme contact.
        - Le transfert d’appel ne fonctionne pas entre les domaines fédérés.
        - Les scénarios de transfert d’appel sont plus limités.
        - La limitation peut être appliquée au trafic fédéré.
- Étant donné cette expérience asymétrique, la prise en charge officielle de la fonctionnalité d’appel dans les scénarios intersites entre un utilisateur local et un utilisateur dans le Cloud qui ne se trouve pas dans l’annuaire local est limitée à l’égal à égal à égal uniquement. 
    - Le transfert d’appel, le transfert, les files d’attente d’appels, etc., entre ces utilisateurs ne sont pas pris en charge.
    - Ces scénarios d’appels non pris en charge apparaîtront toujours activés, mais dans de nombreux cas, ils échoueront de manière imprévisible. 
    - Dans la **[figure D](#figure-d)** ci-dessus, l’utilisateur E est en local et les appels avec les utilisateurs a, B ou C seront uniquement pris en charge en tant qu’homologue à homologue. (Les appels avec l’utilisateur D n’auraient pas de limitations de prise en charge.)  Toutefois, une fois que l’utilisateur local E est déplacé vers le Cloud, cette restriction ne s’applique plus.
- Si vous disposez de plusieurs déploiements de Skype entreprise Server 2019 dans votre environnement, seuls 1 de ces déploiements peuvent être configurés pour utiliser le standard automatique de l’organisation, car cette fonctionnalité nécessite une configuration hybride de Skype entreprise Server. 
- L’ordre de certaines des étapes précédentes peut être ajusté. L’exigence clé devant être satisfaite est que si toutes ces conditions sont vraies :
    - Plusieurs forêts Skype entreprise locales synchronisées avec un client AAD unique
    - Le domaine fractionné est activé avec une forêt locale
    - Au moins un utilisateur de l’organisation hybride a été migré vers le Cloud<br>   Ensuite, vous *devez* désactiver tous les autres domaines SIP en ligne à partir de n’importe quelle autre forêt Skype entreprise locale. Dans le cas contraire, la Fédération entre les utilisateurs en ligne de l’organisation hybride et les utilisateurs locaux d’autres organisations s’arrêtera dans un sens.

## <a name="implications"></a>Implique

- Étant donné qu’il existe des limitations en matière de prise en charge des fonctionnalités d’appel avancées, comme décrit ci-dessus, les **organisations doivent traiter ces États asymétriques comme des transits dans le cadre de la migration, et ne pas les poursuivre en tant qu’état stable**.  
- Les organisations avec plusieurs déploiements Skype entreprise locaux doivent généralement commencer par un déploiement qui peut être entièrement migré vers le Cloud, afin que la consolidation puisse continuer. Il est entendu que, dans certains cas, il y aura holdouts de certains groupes d’utilisateurs pour lesquels il n’est pas encore viable de passer à Teams. Lorsqu’il s’agit d’une considération dans les scénarios impliquant plusieurs forêts Skype entreprise, commencez la migration avec une autre forêt qui n’a pas ces limitations, si possible.
- Lors du passage de l’installation locale au Cloud, les utilisateurs qui ont des relations de délégation et/ou sont généralement impliqués dans les scénarios de transfert d’appel doivent être déplacés ensemble en tant qu’unité.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>Considérations relatives au passage au mode TeamsOnly

Lorsque vous déplacez des utilisateurs de l’environnement local vers le Cloud dans un environnement hybride, vous pouvez les déplacer vers Skype entreprise uniquement ou vers le mode TeamsOnly. *Si vous envisagez de déplacer les utilisateurs vers le mode TeamsOnly, lisez d’abord cette section.*

- Lorsque vous affectez un mode TeamsOnly à un utilisateur, toutes les conversations et tous les appels provenant de n’importe quel autre utilisateur s’affichent dans le client teams de cet utilisateur. 
- Si les utilisateurs de Skype entreprise en local utilisent principalement Skype entreprise client et non Teams, envisagez de définir TeamsUpgradePolicy de sorte que le routage vers les utilisateurs locaux se trouve toujours dans Skype entreprise au lieu de teams. Pour garantir un routage approprié des conversations et des appels entre les utilisateurs qui sont TeamsOnly et ceux qui utilisent encore Skype entreprise sur site, les utilisateurs locaux doivent avoir une valeur effective de TeamsUpgradePolicy avec l’un des modes SfB, et non les îlots (qui est le valeur par défaut). 
    - Pour ce faire, *vous devez d’abord définir l’instance globale de TeamsUpgradePolicy de votre locataire sur l’une des valeurs*suivantes :
        - SfBWithTeamsCollab (recommandé)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - Vous pouvez accorder une stratégie à l’échelle du client à l’aide de la commande suivante :<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - Remarque : vous devez effectuer cette opération à un niveau à l’échelle du client car la stratégie ne peut pas être affectée à des utilisateurs individuels qui n’ont pas d’adresse SIP dans l’annuaire en ligne. Si vous avez désactivé les domaines SIP en ligne pour vos déploiements purs purs, les utilisateurs de ces domaines ne disposeront pas des adresses SIP dans le répertoire en ligne par conception. Par conséquent, le seul moyen d’appliquer une stratégie à ces utilisateurs locaux est d’affecter au niveau du client. En revanche, dans le déploiement hybride, les utilisateurs auront une adresse SIP dans l’annuaire en ligne afin qu’ils puissent être explicitement affectés à une stratégie s’il s’agit d’une valeur différente de la stratégie globale client.
- Le client teams UX n’honore pas encore les modes SfB de TeamsUpgradePolicy. Par exemple, dans ces modes, le lancement des appels et des conversations dans teams est actuellement possible, bien que, à l’avenir, ce ne soit pas le cas. Cela peut entraîner une confusion entre les utilisateurs, car les réponses peuvent parfois apparaître dans teams et parfois dans Skype entreprise, selon les circonstances. Il est recommandé de désactiver séparément l’appel et la conversation via TeamsMessagingPolicy et TeamsCallingPolicy pour les utilisateurs qui sont toujours sur site.

## <a name="see-also"></a>Voir aussi

[Mettre à jour le certificat de serveur Edge](cloud-consolidation-edge-certificates.md)

[Mettre à jour AAD Connect pour inclure plusieurs forêts](cloud-consolidation-aad-connect.md)

[Désactiver le mode hybride pour terminer la migration vers le cloud](cloud-consolidation-disabling-hybrid.md)
