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
ms.openlocfilehash: 3679999bc12f606fe338652e8bef22e455cec9ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>Forum aux questions : approvisionnement de Lync Server 2013 pour la connectivité Skype

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2019-03-22_

À compter du 2019 avril, nous allons arrêter la collecte et la rétention des informations de contact pour les clients qui sont configurés pour la Fédération Skype via le site Web pic.lync.com. Cette modification est effectuée afin de s’assurer que le système de mise en service pic.lync.com adhère aux stratégies de confidentialité de Microsoft. 
 
Une fois que cette modification a lieu, nous ne pourrons plus fournir de mises à jour de messagerie sur les modifications de mise en service en attente. Les modifications de mise en service PIC se terminent généralement dans les 24-48 heures après leur entrée. Si vous rencontrez toujours des problèmes de Fédération Skype 48 heures après avoir soumis une demande de mise en service, contactez le support technique Microsoft pour en savoir plus.

> [!IMPORTANT]
> Dans le cadre de cette modification, toutes les informations de contact précédemment entrées seront purgées de notre système à la fin du 2019 avril.


**Q : Quelles sont les fonctionnalités prises en charge entre Microsoft Lync et Skype ?**

**A :** Avec Skype Now de la famille Microsoft, de nouvelles opportunités d’étendre les scénarios de communications unifiées aux centaines de millions de personnes qui utilisent Skype. Cette combinaison permettra aux clients Lync de se connecter et de collaborer avec des fournisseurs, des clients et des partenaires en s’appuyant sur la richesse de Lync et la portée de Skype.

  - Messages instantanés et appels audio et vidéo — appels audio et vidéo fédérés et messagerie instantanée entre Lync et les utilisateurs de Skype

  - Partage de présence — informations de présence Exchange entre les contacts fédérés

  - Administration simple : paramètres et contrôles permettant de configurer les communications fédérées conformément aux stratégies et normes de votre organisation.

**Q : Comment puis-je qualifier mon déploiement Lync avec Skype ?**

**A :** Vous disposez d’une licence pour la connectivité Skype si vous disposez des éléments suivants :

  - Lync Server (2010 ou 2013) et licences d’accès au client standard Lync Server ("Cal"; 2010 ou 2013) pour les utilisateurs et/ou les appareils de votre organisation qui se connecteront à Skype. 

  - Lync Online (en tant que licences autonomes ou en tant que partie intégrante d’une suite Office 365).Toutefois, ce service (pic.lync.com) est uniquement destiné à la mise en service de Lync Server et des déploiements hybrides Lync Server et Lync Online.Lync Online la mise en service PIC est réalisée dans le panneau de configuration Lync Online (LOCP).

**Q : Quels sont les éléments que les utilisateurs finaux Lync doivent faire pour se connecter aux contacts Skype ?**

**A :** Une fois qu’un domaine est activé et que les fonctionnalités sont activées par l’administrateur Lync d’une organisation, les utilisateurs de Lync peuvent ajouter des contacts Skype à leurs listes de contacts au sein du client Lync.

**Q : que doivent faire les utilisateurs finaux Skype pour se connecter aux contacts Lync ?**

**A :** Tous les utilisateurs de Skype qui souhaitent se connecter à un utilisateur Lync doivent disposer d’un compte Microsoft associé à leur identifiant Skype et se connecter à l’aide du compte Microsoft.Cela peut être activé dans le client Skype.

**Q : est-ce que la Fédération avec Windows Live est toujours disponible ?**

**A :** À compter d’octobre, 2012, Microsoft a commencé à aider les utilisateurs de Windows Live Messenger (WLM) à passer à Skype, en route vers la mise hors ligne de WLM.Lync continuera de prendre en charge la Fédération avec WLM tant que WLM est disponible sur le marché, mais aucune activation de domaine Windows Live supplémentaire ne sera autorisée.Le déplacement d’utilisateurs WLM est activé par Skype 6,0 pour Mac et Windows (publié en octobre 25, 2012), ce qui permet de se connecter à l’aide d’un compte Microsoft (autrement dit, les mêmes informations d’identification que WLM). Une fois qu’il se connecte à Skype, les listes d’amis WLM sont automatiquement renseignées dans Skype, et les utilisateurs peuvent tirer parti des fonctionnalités de communication étendues de Skype telles que l’appel de téléphones fixes et mobiles, le partage d’écran, l’appel vidéo de groupe et la prise en charge d’un large plusieurs appareils.De plus, les contacts Lync fédérés de WLM utilisateurs suivent la transition dans Skype avec le reste de leurs listes d’amis, et la messagerie instantanée entre Skype et Lync pour ces contacts sera immédiatement disponible. Les clients Lync n’ont pas besoin de faire quoi que ce soit pour garantir la continuité du service.

**Q : est-ce que\! la Fédération avec Yahoo ou AOL est toujours disponible ?**

**A :** Nbre. Fédération avec Yahoo\! et AOL étaient subordonnés à la prise en charge de Yahoo\! et AOL.Pour Yahoo\! et AOL, le service s’est terminé le 30 juin 2014. 

**Q : puis-je faire une version d’évaluation de la connectivité Skype avant d’acheter Lync ?**

**A :** La connectivité Skype n’est pas proposée à titre d’évaluation. À la place d’une version d’évaluation, les clients Lync bénéficiant de licences éligibles sont encouragés à s’inscrire simplement pour le service à tester.

**Q : quelles informations sont requises pour la mise en service ?**

**A :** Pour soumettre une demande de mise en service sous une licence qualifiée, vous avez besoin des éléments suivants :

  - Numéro de contrat Microsoft :
    
      - Support de licences en volume Microsoft : numéro de contrat de licence en volume Microsoft
    
      - Réseau partenaire Microsoft : ID de partenaire du siège social
    
      - Contrat de licence du fournisseur de services : numéro d’enregistrement initial
    
      - Services à volume élevé : numéro d’enregistrement de produit

  - Noms de domaine complets (FQDN) pour le service Edge d’accès.
    
      - Nom de domaine complet (FQDN) pour au moins un service Edge d’accès est requis.
    
      - Si votre organisation dispose de plusieurs serveurs exécutant le service Edge d’accès, spécifiez les noms de domaine complets pour chaque service Edge d’accès supplémentaire. Important : Si vous avez précédemment spécifié un nom de domaine complet pour le service Edge d’accès et que vous souhaitez le modifier, l’exécution de la modification peut prendre plusieurs jours et entraîner une interruption du service. Pour empêcher toute interruption de service, nous vous recommandons de conserver le nom de domaine complet précédemment spécifié du service Edge d’accès.

  - Domaine (s) SIP (Session Initiation Protocol). Il s’agit du suffixe de domaine de l’URI SIP que les utilisateurs utilisent actuellement pour la messagerie instantanée. Si votre organisation possède plusieurs domaines SIP, spécifiez le suffixe de domaine pour chaque domaine utilisé pour la messagerie instantanée. Par exemple, pour user1@contoso.com, spécifiez contoso.com pour le domaine SIP ; pour user1@example.fabrikam.com, spécifiez example.fabrikam.com en tant que domaine SIP.
    
    <div>
    

    > [!NOTE]
    > Spécifiez uniquement le suffixe de domaine pour le domaine SIP. Ne spécifiez pas de noms de domaine complets, y compris le nom de domaine complet (FQDN) pour le service Edge d’accès, pour le domaine SIP.

    
    </div>

  - Informations de contact. Spécifiez une adresse de messagerie pour l’administrateur de chaque domaine SIP que vous spécifiez.

**Q : Comment puis-je activer la connectivité Lync-Skype dans un scénario de domaine fractionné ?**

**A :** Si vous avez un scénario de domaine fractionné sur site Lync Online 2013 et Lync Server (avec des utilisateurs sur site et en ligne utilisant le même domaine SIP), activez la connectivité Lync-Skype en effectuant ces deux étapes dans l’ordre suivant

1.  Configurez la connectivité Lync-Skype sur site comme indiqué dans le Guide de mise en service de PIC.

2.  Patientez jusqu’à ce que vous voyez confirmation que votre domaine a été mis en service par Microsoft.

3.  Une fois que vous avez affiché la confirmation, utilisez le centre d’administration Lync pour activer les communications externes. Pour plus d’informations, consultez la rubrique[https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Cette commande est importante.Vous devez configurer la connectivité locale avant d’activer les communications dans Lync Online. Si la commande est contrepassée, les informations entrées pour le local dans <https://pic.lync.com> ne seront pas transmises. Si vous avez déjà configuré Lync Online pour les communications externes avec ce domaine, vous devez le désactiver, patienter 24 heures, puis recommencer, tout d’abord en entrant vos informations <https://pic.lync.com> sur les locaux, puis en activant les communications externes pour Lync Online.

**Q : puis-je configurer plusieurs noms de domaine complets de service Edge d’accès pour la connectivité Skype ?**

**A :** Vous ne pouvez configurer qu’un seul nom de domaine complet du serveur Edge d’accès pour un ou plusieurs domaines. Vous pouvez configurer plusieurs noms de domaine complets d’accès Edge d’accès, jusqu’à 10 par demande, s’ils ont des domaines distincts.

**Q : puis-je obtenir la liste des adresses de messagerie de comptes Microsoft que vous recherchez pour l’organisation qui demande la mise en service ?**

**A :** Nbre. Ces adresses sont considérées comme des informations d’identification personnelle et ne sont pas partagées.

**Q : Comment puis-je ajouter un contact Windows Live Messenger dont l’ID contient un domaine autre que ceux pris en charge par Windows Live ?**

**A :** Si vous ajoutez un utilisateur Windows Live Messenger avec un compte ou un ID avec un domaine non Windows Live, entrez l’adresse au format suivant : \<nom\>d’utilisateur (\<nom\>de domaine) @msn. com, où \<nom\> de domaine est le nom de domaine dans l’adresse de messagerie de l’utilisateur. Par exemple, si vous souhaitez ajouter ted@contoso.com, vous devez utiliser le format suivant : Ted (contoso. com) @msn. com. Pour obtenir la liste des domaines administrés par Windows Live, consultez la section domaines pris en charge dans la section « problèmes connus liés à la messagerie instantanée publique après l’installation de Live Communications Server https://support.microsoft.com/?kbid=897567Service Pack 1 » à l’adresse.

**Q : combien de temps le processus de mise en service prend-il ?**

**A :** La mise en service peut prendre jusqu’à 30 jours.

**Q : Comment puis-je savoir quand la mise en service est terminée ?**

**A :** Microsoft enverra une notification par courrier électronique lorsque la mise en service sera terminée.

**Q : Comment puis-je mettre à jour les informations de configuration ou de contact que j’envoie ?**

**A :** Vous pouvez mettre à jour vos informations sur le site Web que vous avez utilisé pour demander la mise en service, après l’exécution de la mise en service. Entrez votre numéro de contrat, puis cliquez sur mettre à jour le service.

</div>

<span> </span>

</div>

</div>

</div>

