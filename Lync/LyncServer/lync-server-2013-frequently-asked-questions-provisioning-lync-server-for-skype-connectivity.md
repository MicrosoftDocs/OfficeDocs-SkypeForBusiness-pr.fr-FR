---
title: 'Forum aux questions : approvisionnement de Lync Server pour la connectivité Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7204119aca18bfeb2539b0ee5eae5bb53f38efd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Forum aux questions : approvisionnement de Lync Server 2013 pour la connectivité Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2019-03-22_

À compter du 2019 avril, nous mettrons fin à la collecte et la conservation des informations de contact des clients approvisionnés par Skype Federation par le biais du site Web pic.lync.com. Cette modification est apportée pour s’assurer que le système de mise en service de pic.lync.com respecte les politiques de confidentialité de Microsoft. 
 
Lorsque le changement est en cours, nous ne pourrons plus fournir de mises à jour par e-mail sur les changements de mise en service en attente. Les modifications apportées aux mises en service PIC s’effectuent généralement dans les 24-48 heures suivant la saisie. Si vous continuez à rencontrer des problèmes avec la Fédération de Skype 48 heures après avoir envoyé une demande de provisionnement, contactez le support technique de Microsoft pour approfondir votre investigation.

> [!IMPORTANT]
> Dans le cadre de cette modification, toutes les informations de contact précédemment entrées sont purgées de notre système à la fin du 1er avril 2019.


**Q : Quelles sont les fonctionnalités prises en charge entre Microsoft Lync et Skype ?**

**A :** Avec Skype, c’est désormais une nouveauté de la famille Microsoft, de nouvelles possibilités pour développer des scénarios de communications unifiées vers des centaines de millions de personnes qui utilisent Skype. Cette combinaison permettra aux clients de Lync de se connecter et de collaborer avec des fournisseurs, des clients et des partenaires en utilisant la richesse de Lync et la portée de Skype.

  - Messages instantanés et appels audio et vidéo : appels audio et vidéo fédérés et messagerie instantanée entre les utilisateurs de Lync et de Skype

  - Partage de présence : échangez des informations de présence entre des contacts fédérés.

  - Administration simple : paramètres et contrôles qui vous permettent de configurer les communications fédérées conformément aux politiques et normes de votre organisation.

**Q : Comment puis-je qualifier mon déploiement Lync avec Skype ?**

**A :** Vous disposez d’une licence pour la connectivité Skype si vous avez :

  - Lync Server (2010 ou 2013) ainsi que les licences d’accès client de Lync Server standard (« CAL »; 2010 ou 2013) pour les utilisateurs et/ou les appareils de votre organisation qui se connectent à Skype. 

  - Lync Online (en tant que licences autonomes ou dans le cadre d’une suite Office 365).Toutefois, ce service (pic.lync.com) est uniquement destiné à la mise en service de Lync Server et aux déploiements Lync Server et Lync Online.La mise en service de l’image de Lync Online est réalisée dans le panneau de configuration Lync Online (LOCP).

**Q : que doivent faire les utilisateurs finaux de Lync pour se connecter à des contacts Skype ?**

**A :** Après activation d’un domaine et des fonctionnalités activées par l’administrateur de Lync d’une organisation, les utilisateurs de Lync peuvent ajouter des contacts Skype à leurs listes de contacts dans le client Lync.

**Q : que doivent faire les utilisateurs finaux de Skype pour se connecter à des contacts Lync ?**

**A :** Tous les utilisateurs de Skype désireux de se connecter à un utilisateur de Lync doivent disposer d’un compte Microsoft associé à leur identifiant Skype et se connecter à l’aide du compte Microsoft.Cette option peut être activée dans le client Skype.

**Q : est-ce que la Fédération avec Windows Live est toujours disponible ?**

**A :** À compter de octobre, 2012, Microsoft a commencé à aider les utilisateurs de Windows Live Messenger (WLM) à se déplacer dans Skype, en voie pour mettre en place WLM.Lync continuera à prendre en charge la Fédération avec WLM tant que WLM est disponible sur le marché, mais aucune activation supplémentaire du domaine Windows Live ne sera autorisée.Le mouvement des utilisateurs WLM est activé par le Skype 6,0 pour Mac et Windows (publiée le 25 octobre 2012), qui permet de se connecter avec un compte Microsoft (c’est-à-dire, les mêmes informations d’identification que WLM). Après vous être connecté à Skype, WLM Buddy s’est affiché automatiquement dans Skype, et les utilisateurs peuvent profiter des fonctions de communication étendues de Skype, telles que les appels vers des téléphones fixes et mobiles, le partage d’écran, les appels vidéo de groupe et l’assistance pour un large éventail de personnes. divers appareils.De plus, les contacts Lync fédérés de l’utilisateur WLM suivent la transition vers Skype avec le reste de la liste de vos amis et la messagerie instantanée entre Skype et Lync pour ces contacts sera disponible immédiatement. Les clients Lync n’ont rien à faire pour activer cette continuité de service.

**Q : est-ce que\! la Fédération avec Yahoo ou AOL n’est toujours pas disponible ?**

**A :** Aucun. Fédération avec Yahoo\! et AOL étaient dépendants de l’assistance de Yahoo\! et AOL.Pour Yahoo\! et AOL, le service s’est terminé le 30 juin 2014. 

**Q : est-il possible d’essayer une connectivité Skype avant d’acheter Lync ?**

**A :** La connectivité Skype n’est pas proposée dans le cadre de la version d’évaluation. À la place d’une version d’évaluation, les clients Lync disposant de licences éligibles sont invités à s’inscrire simplement au service à des fins de test.

**Q : quelles informations sont requises pour la configuration ?**

**A :** Pour renvoyer une demande de mise en service en vertu d’une licence qualifiée, vous devez disposer des éléments suivants :

  - Numéro de contrat Microsoft :
    
      - Support du programme de licence en volume Microsoft : numéro de contrat de licence en volume Microsoft
    
      - Partenaire Microsoft : ID de partenaire du siège social
    
      - Contrat de licence de prestataire de services : numéro d’inscription initial
    
      - Services à volume élevé : numéro d’inscription du produit

  - Noms de domaine complets (FQDN) du service Edge d’accès.
    
      - Le FQDN d’au moins un service Edge d’accès est requis.
    
      - Si votre organisation possède plusieurs serveurs exécutant le service Edge d’accès, spécifiez les noms de domaine complets (FQDN) de chaque service Edge d’accès supplémentaire. Important : Si vous avez précédemment spécifié un nom de domaine complet pour le service Edge d’accès et que vous souhaitez le modifier, la mise en service de la modification peut prendre plusieurs jours et provoquer une interruption du service. Pour éviter toute interruption du service, nous vous recommandons de conserver le nom de domaine complet (FQDN) du service Edge d’accès spécifié.

  - Domaines SIP (Session Initiation Protocol). Il s’agit du suffixe de domaine de l’URI SIP que les utilisateurs utilisent actuellement pour la messagerie instantanée. Si votre organisation possède plusieurs domaines SIP, spécifiez le suffixe de domaine pour chaque domaine utilisé pour la messagerie instantanée. Par exemple, pour user1@contoso.com, spécifiez contoso.com pour le domaine SIP. pour user1@example.fabrikam.com, spécifiez example.fabrikam.com comme domaine SIP.
    
    <div>
    

    > [!NOTE]
    > Spécifiez uniquement le suffixe de domaine pour le domaine SIP. Ne spécifiez pas de FQDN, y compris le nom de domaine complet (FQDN) du service Edge d’accès, pour le domaine SIP.

    
    </div>

  - Les informations de contact. Spécifiez l’adresse de messagerie de l’administrateur de chaque domaine SIP que vous spécifiez.

**Q : Comment puis-je activer Lync-connectivité Skype dans un scénario à domaines répartis ?**

**A :** Si vous avez un scénario Lync Online 2013 et Lync Server local Split-Domain (avec des utilisateurs en ligne et sur site utilisant le même domaine SIP), activez Lync-connectivité Skype en effectuant les deux étapes suivantes dans l’ordre suivant :

1.  Configurez la connectivité Lync-Skype sur site comme décrit dans le Guide de mise en service de l’application PIC.

2.  Patientez jusqu’à ce que vous voyiez une confirmation de mise en service de votre domaine par Microsoft.

3.  Une fois la confirmation affichée, utilisez le centre d’administration Lync pour activer les communications externes. Pour plus d’informations, reportez-vous à[http://office.microsoft.com/en-us/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/en-us/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Cet ordre est important.Vous devez configurer la connectivité locale avant d’activer les communications dans Lync Online. Si la commande est contrepassée, les informations entrées pour la version locale ne <https://pic.lync.com> seront pas déplacées. Si vous avez déjà configuré Lync Online pour les communications externes avec ce domaine, vous devez le désactiver, patienter 24 heures, et recommencer en entrant vos informations <https://pic.lync.com> sur site, puis en activant les communications externes pour Lync Online.

**Q : est-il possible de configurer plusieurs noms de domaine complets de service Edge d’accès pour la connectivité Skype ?**

**A :** Vous ne pouvez configurer qu’un nom de domaine complet (FQDN) d’accès pour un ou plusieurs domaines. Vous pouvez configurer plusieurs noms de domaine complets d’accès Edge pour un maximum de 10 par demande, s’ils possèdent des domaines distincts.

**Q : est-il possible d’obtenir la liste des adresses de messagerie de compte Microsoft que vous recherchez pour l’organisation demandant la mise en service ?**

**A :** Aucun. Ces adresses sont considérées comme des informations d’identification personnelle et ne sont pas partagées.

**Q : Comment puis-je ajouter un contact Windows Live Messenger possédant un ID contenant un domaine autre que ceux pris en charge par Windows Live ?**

**A :** Si vous ajoutez un utilisateur Windows Live Messenger avec un compte ou un ID possédant un domaine autre que Windows Live, entrez l’adresse au format suivant : \<nom\>d’utilisateur\<(nom\>de domaine) @msn. com \<, où\> nom de domaine est le nom de domaine dans l’adresse de courrier de l’utilisateur. Par exemple, si vous voulez ajouter ted@contoso.com, vous devez utiliser le format suivant : Ted (contoso. com) @msn. com. Pour obtenir la liste des domaines qui sont administrés par Windows Live, voir la section domaines pris en charge dans « problèmes connus qui se produisent avec la messagerie instantanée publique après l’installation de Live http://support.microsoft.com/?kbid=897567Communications Server Service Pack 1 ».

**Q : combien de temps le processus de mise en service prend-il en charge ?**

**A :** La mise en service peut durer jusqu’à 30 jours.

**Q : Comment puis-je savoir à quel moment la mise en service sera terminée ?**

**A :** Microsoft enverra une notification par courrier électronique lors de la mise en service.

**Q : Comment puis-je mettre à jour les détails de la configuration ou du contact que j’ai envoyés ?**

**A :** Vous pouvez mettre à jour vos informations sur le site Web que vous avez utilisé pour demander la mise en service, une fois la mise en service terminée. Entrez votre numéro de contrat, puis cliquez sur mettre à jour le service.

</div>

<span> </span>

</div>

</div>

</div>

