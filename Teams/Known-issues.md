---
title: Problèmes connus pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 4/18/2018
ms.topic: article
ms.service: msteams
ms.reviewer: marcl, ninadara, v-leslc
description: Liste actuelle des problèmes connus pour l'application client et l'expérience administrateur de Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c8ce7b7d53e03ae265f41105dabd09978a62e61
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2018
---
# <a name="known-issues-for-microsoft-teams"></a>Problèmes connus pour Microsoft Teams
  
Cet article répertorie les problèmes connus pour les Teams de Microsoft, par domaine de fonctionnalité.
## 

## <a name="administration"></a>Administration
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Gestion des administrateurs de connecteurs de clients à l’échelle n’est plus disponible  <br/> |Lorsque vous tentez d’ajouter un connecteur dans client et une version en ligne nous obtenons l’erreur : une erreur inattendue s’est produite. Essayez à nouveau. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Désactiver les paramètres d’équipes. Consultez l’article de la prise en chargehttps://msdn.microsoft.com/en-us/microsoft-teams/connectors  <br/> |21.06.2017  <br/> |

## <a name="apps"></a>Applications
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Options de connecteur est manquante pour certaines équipes  <br/> |Lorsque vous cliquez avec le bouton droit sur un canal, l'option Connecteurs ne s'affiche pour aucun membre de l'équipe.  <br/> |Le créateur de l'équipe doit posséder une boîte aux lettres en ligne. Sinon, l'option Connecteur n'est pas disponible. Il s'agit d'un comportement normal.  <br/> |26.06.2017  <br/> |

## <a name="authentication"></a>Authentification
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsque vous tentez d'ouvrir Teams sur Internet Explorer ou Edge, une boucle se produit ou le programme se bloque et ne se connecte pas.   <br/> | Votre organisation utilises la fonction de sites approuvés dans Internet Explorer et l'application Web Teams n'est pas correctement journalisée car les sites approuvés pour Teams ne sont pas autorisés. <br/>|Dans les paramètres d'IE, effectuez les modifications suivantes à l'aide de droits d'administrateur ou d'un objet de stratégie de groupe :<br/><ol><li>Sous **Options de Internet** &gt; **Privacy** &gt; **Avancé**, accepter les cookies internes et tierce partie et activez la case à cocher pour **toujours autoriser les cookies de session**.</li><li>Cliquez sur **Options Internet** &gt; **Sites de confiance** &gt; **Sites**et ajoutez tous les éléments suivants :<ul><li>https://\*.microsoft.com</li><li>https://\*.microsoftonline.com</li><li>https://\*.teams.skype.com</li><li>https://\*.teams.microsoft.com</li><li>https://\*.sfbassets.com</li><li>https://\*.skypeforbusiness.com</li></ul></li></ol><br/><b>REMARQUE</b> : Validez et autorisez toujours les URL approuvées pour Teams et les conditions requises figurant dans le document suivant : [URL et plages d'adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).   <br/> |01.11.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Restrictions du complément Outlook  <br/> |Pour utiliser le complément Outlook, vous devez vous connecter à Teams au moyen de l'authentification multifacteur (MFA). Si la MFA échoue au cours de la procédure de connexion, vous pourrez toujours vous connecter à Teams, mais un message d'erreur s'affichera lorsque vous essayerez d'utiliser le complément.  <br/> Pour l'instant, le complément est uniquement disponible pour les utilisateurs Windows.  <br/> Le complément ne fonctionnera pas si vous utilisez une authentification par proxy.  <br/> | Aucune solution. <br/> |02.08.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Teams de Microsoft sera toujours ouvrir une session sur le compte d’ordinateur joint au domaine.   <br/> |Si un utilisateur dispose de deux comptes d’équipes différentes et a un ordinateur à un domaine activé, équipes utilisera le profil à un domaine sur l’ordinateur pour vous connecter automatiquement l’utilisateur dans les équipes. Pour basculer vers le compte d’autres équipes, l’utilisateur doit se déconnecter de l’application et entrer des informations d’identification pour le deuxième compte pour vous connecter manuellement. Si l’utilisateur se déconnecte d’équipes et redémarre l’ordinateur, lors du redémarrage, équipes seront connecteront automatiquement en utilisant le profil à un domaine. <br/> | Aucune solution. <br/> |02.08.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Échec d’authentification modernes - authentification de formulaires non activée  <br/> |Si l'authentification multifacteur échoue, réalisez l'authentification depuis l'application web.  <br/> Pour plus d'informations, voir [Prise en charge du paramètre des services ADFS prompt=login](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Vérifiez ce paramètre :Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled.  <br/> |19.06.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Module de génération de session unique (SSO) <br/> |L'authentification unique (SSO) ne s'applique pas au planificateur. Vous devrez vous reconnecter à la première utilisation du planificateur sur chaque client.  <br/> |Aucune solution. Nous travaillons actuellement sur d'autres améliorations du système d'authentification.  <br/> |28.02.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d'enregistrer la photo de profil  <br/> |Les utilisateurs ne peuvent pas enregistrer leur photo de profil lorsque la boîte aux lettres Exchange est hébergée sur site.  <br/> |Aucune solution.  <br/> |28.02.2017  <br/> |

## <a name="browser"></a>Navigateur
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Artéfacts verts dans le rendu vidéo Chrome  <br/> |Artefacts verts s’affichent lors de l’affichage vidéo ou de partage de l’écran dans un appel ou meetup de Chrome.  <br/> |Désactivez le paramètre d'accélération matérielle dans Chrome.  <br/> |03.08.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Prise en charge du client web par Safari  <br/> |Les utilisateurs qui essayent d'ouvrir le client web de Microsoft Teams dans Safari sont redirigés pour télécharger le client de bureau. Microsoft étudie la prise en charge de Safari et communiquera les mises à jour au moyen de [la Feuille de route de Teams](http://aka.ms/TeamsRoadmap).  <br/> |Utilisation prise en charge des navigateurs internet, qui incluent : Internet Explorer 11 +, Microsoft Edge 12 +, Chrome 51.0 + et Firefox 47.0 +.  <br/> |02.11.2016  <br/> |

## <a name="channels"></a>Canaux
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsqu’un utilisateur quitte la société, il apparaît dans Teams de Microsoft en tant que « Utilisateur inconnu »<br/> |Lorsqu’un utilisateur quitte la société, il apparaît dans Teams de Microsoft en tant que « Utilisateur inconnu ». En outre, l’onglet conversation affiche : « utilisateur inconnu a été ajouté à l’équipe. » Problème classé sous :https://domoreexp.visualstudio.com/MSTeams/_workitems/edit/168830  <br/> |Aucune solution.  <br/> |9/12/17  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas recréer un nom de canal préexistant.  <br/> |Une fois qu'un nom de canal a été défini, même si le canal est supprimé, le nom ne peut pas être réutilisé. Notre système conserve ces données pour des raisons de protection des informations.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/> |

## <a name="chat"></a>Conversation

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|@ Mentionne pour message supprimé Envoyer notification avec la liaison de canal  <br/> |Il existe une limitation connue de notification lorsque vous êtes au-mentionné dans un message qui est supprimé ; la notification de l’aliment pour animaux va accéder au canal, mais pas pour un message spécifique. <br/> | Par conception <br/> | 3/28/17  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs sur site de Skype Entreprise ne reçoivent pas mes messages  <br/> |Les messages ne sont pas acheminés lorsque les utilisateurs de Microsoft Teams essayent d'envoyer un message à une autre personne qui utilise Skype Entreprise sur site.  <br/> | L'interopérabilité entre Teams et les utilisateurs hébergés sur Skype Entreprise Online est prise en charge. Les utilisateurs de Teams peuvent envoyer des conversations en tête-à-tête à des personnes qui n’utilisent pas Teams à l'aide de Skype Entreprise Online. <br/> L'interopérabilité entre Teams et les utilisateurs hébergés sur Skype Entreprise sur site n'est pas prise en charge. Les utilisateurs de Teams ne peuvent pas envoyer de conversations en tête à tête à des utilisateurs qui utilisent Skype Entreprise sur site.  <br/> |02.11.2016  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs sur site de Skype Entreprise ne reçoivent pas mes messages  <br/> |Les messages ne sont pas acheminés lorsque les utilisateurs de Microsoft Teams essayent d'envoyer un message à une autre personne qui utilise Skype Entreprise sur site. <br/> | L'interopérabilité entre Teams et les utilisateurs hébergés sur Skype Entreprise Online est prise en charge. Les utilisateurs de Teams peuvent envoyer des conversations en tête-à-tête à des personnes qui n’utilisent pas Teams à l'aide de Skype Entreprise Online. <br/> L'interopérabilité entre Teams et les utilisateurs hébergés sur Skype Entreprise sur site n'est pas prise en charge. Les utilisateurs de Teams ne peuvent pas envoyer de conversations en tête à tête à des utilisateurs qui utilisent Skype Entreprise sur site. <br/> |02.11.2016  <br/> |

## <a name="client"></a>Client
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les équipes ne met pas à jour automatiquement   <br/> | Lorsque Microsoft Teams est installé pour les fichiers de programme à l’aide de scripts d’installation plutôt que l’emplacement par défaut, le client n’auto-mise à jour lorsque de nouvelles versions sont disponibles.    <br/> | À la conception. Veillez à installer l’application dans l’emplacement par défaut : user\Appdata.  <br/> | 9/7/17  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lien symbolique ou mappying un lecteur dans C:\users entraîne l’application à lancer pour un écran blanc  <br/> | Lorsque Microsoft Teams est installé pour les fichiers de programme à l’aide de scripts d’installation plutôt que l’emplacement par défaut, le client n’auto-mise à jour lorsque de nouvelles versions sont disponibles.   <br/> | À la conception. Veillez à installer l’application dans l’emplacement par défaut : user\Appdata. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.  <br/> | 9/7/17  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lien symbolique ou le mappage d’un lecteur dans c:\users entraîne l’application à lancer pour un écran blanc  <br/> |Lorsque l’emplacement par défaut de C:\users\<utilisateur > \appData est modifiée en déplaçant le dossier C:\users ou à l’aide du lien symbolique, l’application démarre avec un écran blanc.   <br/> |Il n’existe aucune solution de contournement connue. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.   <br/> |13.03.2017  <br/> |

## <a name="environment"></a>Environnement
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L'archivage des boîtes aux lettres de groupe (stockage supplémetaire) n'est pas activé.  <br/> |Dans le Centre de sécurité et conformité Office 365, les administrateurs généraux n'ont pas la possibilité d'activer l'archivage pour les boîtes aux lettres de groupe. Cela est possible uniquement pour les boîtes aux lettres utilisateur.  <br/> |Si la capacité de la boîte aux lettres de groupe est presque atteinte, prenez contact avec le support de Microsof Office pour augmenter la capacité.  <br/> |01.02.2017  <br/> |

## <a name="guest-access"></a>Accès invité
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les clients des pays de l'UE et de la région APAC reçoivent une erreur lorsqu'ils ajoutent un utilisateur invité à partir d'un autre client.    <br/> | Les clients des pays de l'UE et de la région APAC subissent un retard de réplication entre Microsoft Teams et Azure Active Directory. Lorsqu'un utilisateur d'un client d'un pays de l'UE ou de la région APAC tente d'ajouter un utilisateur invité d'un autre client, il reçoit un message d'erreur indiquant de réessayer.   <br/> |Cliquez sur le bouton Réessayer pour ajouter l'utilisateur invité.  <br/> |08.11.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Wiki non créé pour les canaux créés par les invités  <br/> |Lorsqu'un invité crée un nouveau canal, l'onglet **Wiki** n'est pas créé. Il n'existe pas de méthode pour joindre manuellement un onglet **Wiki** au canal. <br/> |Aucune solution.  <br/> |20.09.2017  <br/>|

## <a name="meetings"></a>Réunions
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas accéder aux réunions/connecteurs mais ont des boîtes aux lettres Exchange Online. <br/> |Client activement bloque EWS auprès des services dans Exchange Online, mais qu’il doit être compatible avec des stratégies EWS à MS Teams. <br/> |Pour rendre MS Teams conforme, vous devez ajouter la chaîne d’Agent utilisateur pour MS Teams de la EWSAllowList : *skypespaces*, y compris les astérisques. Est de l’intégralité de la commande : set-organizationconfig - ewsallowlist *skypespaces*<br/> Pour plus d’informations :https://technet.microsoft.com/en-us/library/aa997443(v=exchg.160).aspx <br/> |5/30/17  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise est requis pour certaines réunions.  <br/> |Votre calendrier de rendez-vous s'affiche de manière pratique dans Microsoft Teams. Pour participer à une réunion, cliquez sur le bouton **Rejoindre**. <br/> Nous poursuivons le développement à ce sujet, mais pour le moment, si la réunion était planifiée au moyen de Skype Entreprise et que vous cliquez sur **Rejoindre**, Microsoft Teams lance votre client Skype Entreprise pour finaliser votre accès à la réunion. Les réunions planifiées dans Microsoft Teams s'ouvrent directement dans le produit.  <br/> À l'avenir, nous uniformiserons cette procédure.  <br/> |Cliquez sur **Rejoindre**. Microsoft Teams décidera judicieusement si Skype Entreprise est requis pour qu'un utilisateur rejoigne la réunion en fonction de l'URL mentionnée dans la description de la réunion.  <br/> |13.03.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Manque de **réunions**d’être découverts à l’aide de la découverte automatique Exchange. <br/> Teams de Microsoft ne prend pas en charge les boîtes aux lettres hébergées dans Exchange sur l’icône dans la barre de navigation de gauche <br/> |L’icône de **réunion** dans la barre de l’application est actuellement activé pour les utilisateurs de boîte aux lettres est sur mutualisée d’Office 365 et select peu dédié aux utilisateurs dont l’emplacement de boîte aux lettres est peut - locaux et Exchange dédié. Nous étudions actuellement ce problème. Toutefois, aucun délai n'est fixé pour la distribution de cette fonctionnalité.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Nombre maximum de participants pour les réunions  <br/> |Chaque réunion Microsoft Teams peut accueillir jusqu'à 80 participants.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Réunions non disponibles  <br/> |La fonctionnalité et l'icône Réunion ne sont pas disponibles lorsque la boîte aux lettres Exchange est hébergée sur site.  <br/> |Effectuez une mise à niveau vers Exchange 2016 CU3 ou une version suivante pour le déploiement sur site.  <br/> |28.02.2017  <br/> |

## <a name="mobile"></a>Mobile
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune  <br/> |Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune.  <br/> |Aucune solution.  <br/> |20.09.2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d’utiliser le fun sélecteur ou Giphys ou tous les autocollants dans une application mobile  <br/> |Vous ne pouvez pas utiliser des images GIF, emojis ou tous les autocollants sur les clients mobiles.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Différences de mise en page des équipes de Client mobile  <br/> |Les équipes sont présentées dans l’ordre alphabétique et les canaux ne peuvent pas être réduits sur le client mobile.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/>|

## <a name="people"></a>Personnes
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Photos de profil utilisateur  <br/> | Actuellement les équipes ne dispose pas d’un mécanisme pour empêcher les utilisateurs de modifier des photos. L’équipe BTS a atteint avec l’équipe de développement qui a classé les suivantes à titre onéreux : fonctionnalité 108874 : stratégie informatique pour désactiver le chargement de la Photo de profil   <br/> | Si vous avez des clients qui souhaiteraient la possibilité d’empêcher le téléchargement de la Photo de profil dans des équipes, demandez-leur d’ajouter leurs cas de voix et de l’entreprise à commentaires ici :https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos
 <br/> |3/1/17 <br/> |

## <a name="provisioning"></a>Mise en service
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Utilisateur SharePoint incorrect créé pour le site SharePoint de Microsoft Teams  <br/> |Le créateur SharePoint d'un groupe Microsoft Teams est un administrateur SharePoint, pas l'utilisateur correct.  <br/> Lors d'un audit depuis la console d'administration SharePoint, le créateur de la page de collection de sites associé au groupe Office 365 créé pour l'équipe dans Microsoft Teams est l'administrateur SharePoint.  <br/> |Aucune solution.  <br/> |21.07.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs n'arrivent pas à créer une équipe.  <br/> |Votre entreprise peut avoir défini une politique limitant les personnes qui peuvent créer des groupes ou des équipes Office 365.  <br/> |Consultez votre administrateur informatique pour comprendre la politique de votre entreprise en matière de création de groupes et d'équipes.  <br/> |13.03.2017  <br/> |

## <a name="tabs"></a>Onglets
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglets ne fonctionnent ne pas depuis l’activation de l’accès conditionnel <br/> |Certains onglets ne se chargent pas plus dans le Client de bureau dans la mesure où l’accès conditionnel a été activée sur le client. Les onglets de charger lorsque vous utilisez le Client Web. Certains onglets qui peuvent être affectés sont les suivants : PowerBI, formulaires, VSTS, PowerApps et liste SharePoint.  <br/> |Pour afficher les onglets concernés, vous devez utiliser des équipes de bord, Internet Explorer ou Chrome avec l’extension Windows 10 comptes installée. Certains onglets dépendent toujours de l’authentification web, ce qui ne fonctionne pas dans le Client de bureau lorsque l’autorité de certification est activée. Nous travaillons en collaboration avec les partenaires pour activer ces scénarios ; jusqu'à présent, nous avons activé Planner, OneNote et flux de données. <br/> |4/5/18  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste des espaces de travail n'est pas triée par ordre alphabétique.  <br/> |Les utilisateurs qui passent d'un espace de travail à un autre lors de l'ajout d'un onglet PowerBI sont invités à choisir celui qu'ils souhaitent activer parmi une liste non classée par ordre alphabétique.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La barre de défilement disparaît quand des rapports sont sélectionnés.  <br/> |Les utilisateurs qui ajoutent des rapports PowerBI ne peuvent pas faire défiler une liste plus longue que la taille d'un écran de rapports sans perdre leur barre de défilement.  <br/> |Utilisez les flèches vers le haut et vers le bas pour faire défiler la liste.  <br/> |13.03.2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Équipes module intégration Planner en ligne <br/> |Les compartiments de tâches dans le planificateur n’apparaissent pas dans l’expérience en ligne du module.  <br/> |Aucune solution. <br/> |28.02.2017  <br/>|

## <a name="teams"></a>Teams
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Le chargement de photos dans Teams n'est pas bloqué dans OWA/Outlook comme le requiert la stratégie   <br/> | Teams permet aux utilisateurs de charger des photos directement dans Office 365, en dépit des paramètres de stratégie définis pour empêcher cette action dans OWA.   <br/> |<br/>  |16.10.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste d'équipes publiques n'affiche pas toutes les équipes  <br/> |La liste des équipes publiques repose sur Microsoft Graph.  <br/> |Si une équipe n'est pas affichée, essayez de la rechercher au moyen du champ de recherche situé dans le coin supérieur droit.  <br/> | 21.07.2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les noms d’équipe qui contiennent des caractères spéciaux peuvent créer des erreurs de création de la réunion  <br/> |Utilisateur recevra le message **d’erreur** en rouge lors de la tentative de création d’une réunion d’une équipe qui a des caractères spéciaux dans le nom.   <br/> |Renommer ou recréer l’équipe avec un nom qui ne contient-elle pas un « / ».  <br/> |13.07.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un nom d’équipe avec un &amp; symbole qu’il interrompt la fonctionnalité du connecteur  <br/> |Lorsqu'un nom d'équipe est créé avec le symbole &amp;, les connecteurs de l'équipe ou du groupe ne peuvent pas être établis.  <br/> |N'utilisez pas de caractères spéciaux dans le nom des équipes.  <br/> |21.06.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Maximum de 2500 membres par équipe  <br/> |Chaque équipe Microsoft Team peut accueillir un maximum de 2500 membres.  <br/> |Aucune solution.  <br/> |13.03.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La suppression d'une équipe supprime également le groupe associé à celle-ci  <br/> |Il est possible que les utilisateurs ne réalisent pas que le groupe Office 365 sous-jacent est supprimé lorsque l'équipe est supprimée. En outre, si le groupe Office 365 sous-jacent est supprimé, l'équipe l'est également.  <br/> |Les langues supplémentaire dans Microsoft Teams fournissent cette information à l'utilisateur. Cette information n'est pas disponible dans l'interface Groupes Office 365. Votre service d’assistance peut récupérer une groupe/équipe supprimé.  <br/> |13.03.2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|  
|Application de bureau équipes Afficher écran blanc  <br/> | <br/> |Essayez de supprimer ou réinstaller les pilotes graphiques sur l’ordinateur, ou démarrer des équipes à partir de la ligne de commande avec un indicateur de désactivation de GPU :<ul><li>Pour Windows : Ouvrir l’invite de commande et tapez ce qui suit : cd %localappdata%\microsoft\teams\current exécuter Teams.exe--désactiver-gpu</li><li>Pour Mac : Le Terminal de démarrer et entrez ce qui suit : cd \Applications dossier Microsoft\ Teams.app/Contents/MacOS/Teams--désactiver-gpu</li></ul> <br/> |<br/> |

