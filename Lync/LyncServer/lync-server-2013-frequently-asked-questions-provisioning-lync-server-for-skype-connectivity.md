---
title: "Lync Server 2013 : FAQ : approv. de Lync Server pour la conn. Skype"
TOCTitle: 'Forum aux questions : approvisionnement de Lync Server pour la connectivité Skype'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn440172(v=OCS.15)
ms:contentKeyID: 59602866
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Forum aux questions : approvisionnement de Lync Server 2013 pour la connectivité Skype

 

_**Dernière rubrique modifiée :** 2016-12-27_

**Q : quelles fonctionnalités sont prises en charge entre Microsoft Lync et Skype ?**

**R :** l'intégration de Skype à la gamme Microsoft offre de nouvelles possibilités en termes de développement des scénarios de communications unifiées pour des centaines de millions d'utilisateurs de Skype. Cette combinaison permettra aux clients Lync de tirer parti des fonctionnalités enrichies de Lync et de la portée de Skype pour se connecter et collaborer avec des fournisseurs, clients et partenaires.

  - Messagerie instantanée et appels audio et vidéo : fédération des appels audio et vidéo et de la messagerie instantanée entre les utilisateurs Lync et Skype

  - Partage de la présence : informations de présence Exchange entre les contacts fédérés

  - Administration simple : paramètres et contrôles pour la configuration des communications fédérées conformément aux stratégies et normes de votre organisation

**Q : comment remplir les conditions requises pour connecter mon déploiement Lync à Skype ?**

**R :** vous pouvez bénéficier de la connectivité Skype si vous avez :

  - Lync Server (2010 ou 2013) et des licences d'accès client (CAL) Lync Server Standard (2010 ou 2013) pour les utilisateurs et/ou les appareils dans votre organisation qui se connecteront à Skype, OU

  - Lync Online (sous forme de licences autonomes ou dans le cadre d'une suite Office 365). Toutefois, ce service (pic.lync.com) sert uniquement à l'approvisionnement de Lync Server et des déploiements Lync Server et Lync Online hybrides. L'approvisionnement des informations PIC Lync Online est effectué dans le panneau de configuration Lync Online.

**Q : que doivent faire les utilisateurs Lync pour se connecter aux contacts Skype ?**

**R :** après l'activation d'un domaine et des fonctionnalités par l'administrateur Lync d'une organisation, les utilisateurs Lync peuvent ajouter des contacts Skype à leur liste de contacts au sein du client Lync.

**Q : que doivent faire les utilisateurs Skype pour se connecter aux contacts Lync ?**

**R :** les utilisateurs Skype qui souhaitent se connecter à un utilisateur Lync doivent avoir un compte Microsoft associé à leur ID Skype et se connecter à l'aide du compte Microsoft. Ceci peut être activé dans le client Skype.

**Q : la fédération avec Windows Live est-elle toujours disponible ?**

**R :** depuis octobre 2012, Microsoft a commencé à accompagner la transition des utilisateurs Windows Live Messenger (WLM) vers Skype, avant la mise hors service programmée de WLM. Lync continuera de prendre en charge la fédération avec WLM tant que WLM est commercialisé, mais aucune activation de domaine Windows Live ne sera autorisée. La migration des utilisateurs WLM est assurée via Skype 6.0 pour Mac et Windows (publié le 25 octobre 2012) qui permet de se connecter à l'aide d'un compte Microsoft (soit les mêmes informations d'identification que WLM). Une fois l'utilisateur connecté à Skype, les listes de contacts WLM sont renseignées automatiquement dans Skype. L'utilisateur peut alors tirer parti des fonctionnalités de communication étendues de Skype (appel de téléphones fixes et mobiles, partage d'écran, vidéoconférence et prise en charge d'une plus grande variété d'appareils). Par ailleurs, les contacts Lync fédérés des utilisateurs WLM suivent la transition vers Skype avec le reste de leurs listes de contacts, et la messagerie instantanée entre Skype et Lync pour ces contacts sera disponible immédiatement. Les clients Lync n'ont pas besoin de faire quoi que ce soit pour assurer la continuité du service.

**Q : la fédération avec Yahoo\! et AOL est-elle toujours disponible ?**

**R :** la fédération avec Yahoo\! et AOL approche de son terme pour les clients de Lync et Office Communications Server. La capacité de Microsoft à fournir ces services est conditionnée par le support de Yahoo\! et AOL. Or, les accords associés arrivent à leur fin. Pour Yahoo\! et AOL, le service sera maintenu jusqu'en juin 2014.

  - Yahoo : le service sera maintenu jusqu'en juin 2014. Les clients doivent toujours disposer de la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License). Depuis le 1er septembre 2012, la licence PIC USL n'est plus disponible et ne peut pas être achetée ou renouvelée. Les clients ayant acheté une licence avant cette date pourront continuer à assurer la fédération avec Yahoo\! jusqu'à la date d'arrêt du service ou l'expiration de leur licence. Les clients détenteurs de licences PIC dans le cadre d'accords valables au-delà du 30 juin 2014 recevront un crédit proportionnel au montant des paiements et destiné à couvrir la période suivant le 30 juin 2014.

  - AOL : le service de connectivité PIC de Lync ne sera plus disponible à partir du 30 juin 2014. Afin de limiter les perturbations au niveau des clients à la fin du service, nous avons interrompu l'approvisionnement de domaines client supplémentaires. Jusqu'au 30 juin 2014, les clients n'ont rien de spécial à faire pour continuer à prendre en charge les communications fédérées avec AIM. Au-delà de cette date (ou pour les clients qui souhaitent approvisionner d'autres domaines pendant cette période), un service de remplacement est disponible directement auprès d'AOL. Pour plus d'informations sur le nouveau service d'AOL, voir <http://aimenterprise.aol.com/pic.php> (ce lien ouvre une nouvelle page sur AOL.com). 

**Q : puis-je tester la connectivité Skype avant d'acheter Lync ?**

**R :** la connectivité Skype n'est pas proposée sur la base d'une évaluation. Les clients Lync dotés de licences éligibles sont encouragés à s'inscrire au service pour le tester.

**Q : quelles informations sont requises pour l'approvisionnement ?**

**R :** pour envoyer une demande d'approvisionnement en lien avec une licence éligible, vous avez besoin des informations suivantes :

  - Numéro de contrat Microsoft :
    
      - Support du programme de licences en volume Microsoft : numéro de contrat de licences en volume Microsoft
    
      - Microsoft Partner Network : ID siège social partenaire
    
      - Contrat de licence Service Provider : numéro d'inscription initial
    
      - Services haut volume : numéro d'inscription du produit

  - Noms de domaine complets du service Edge d'accès.
    
      - Le nom de domaine complet d'au moins un service Edge d'accès est requis.
    
      - Si le service Edge d’accès est exécuté sur plusieurs serveurs de votre organisation, spécifiez les noms de domaine complets de chaque service Edge d’accès supplémentaire. Important : si vous avez précédemment spécifié un nom de domaine complet pour le service Edge d’accès et souhaitez le modifier, l’approvisionnement de la modification peut prendre plusieurs jours et perturber le service. Pour empêcher les perturbations de service, il est recommandé de maintenir le nom de domaine complet précédemment spécifié du service Edge d’accès.

  - Domaine(s) SIP (Session Initiation Protocol). Il s'agit du suffixe de domaine de l'URI SIP utilisé actuellement par les utilisateurs pour la messagerie instantanée. Si votre organisation a plusieurs domaines SIP, spécifiez le suffixe de chaque domaine utilisé pour la messagerie instantanée. Par exemple, pour utilisateur1@contoso.com, spécifiez contoso.com pour le domaine SIP. Pour utilisateur1@exemple.fabrikam.com, spécifiez exemple.fabrikam.com comme domaine SIP.
    
    > [!NOTE]  
    > Spécifiez uniquement le suffixe du domaine SIP. Ne spécifiez aucun nom de domaine complet, y compris celui du service Edge d'accès, pour le domaine SIP.

  - Informations de contact. Indiquez une adresse de messagerie pour l'administrateur de chaque domaine SIP que vous spécifiez.

**Q : comment puis-je activer la connectivité Lync-Skype dans un scénario de domaine séparé ?**

**R :** en cas de scénario de domaine séparé avec Lync Online 2013 et la version locale de Lync Server (les utilisateurs des versions en ligne et locale utilisant le même domaine SIP), vous pouvez activer la connectivité Lync-Skype en effectuant les deux étapes ci-après dans l'ordre suivant :

1.  Configurez la connectivité Lync-Skype locale comme décrit dans le guide d'approvisionnement des informations PIC.

2.  Attendez la confirmation d'approvisionnement de votre domaine par Microsoft.

3.  Une fois que vous avez consulté la confirmation, utilisez le centre d'administration Lync pour activer les « communications externes ». Pour plus d'informations, voir [http://office.microsoft.com/fr-fr/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](http://office.microsoft.com/fr-fr/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

Cet ordre est important. Vous devez configurer la connectivité locale avant d'activer les communications dans Lync Online. Si l'ordre est inversé, les informations entrées pour la version locale dans <https://pic.lync.com> ne seront pas transmises. Si vous avez déjà configuré Lync Online pour les communications externes avec ce domaine, vous devez le désactiver, attendre 24 heures, puis recommencer en commençant par entrer vos informations locales dans <https://pic.lync.com>, puis en activant les communications externes pour Lync Online.

**Q : puis-je approvisionner plusieurs noms de domaine complets de service Edge d'accès pour la connectivité Skype ?**

**R :** vous pouvez approvisionner jusqu'à dix noms de domaine complets de service Edge d'accès avec chaque demande d'approvisionnement.

**Q : puis-je obtenir la liste des adresses de messagerie de compte Microsoft déclarées pour l'organisation faisant la demande d'approvisionnement ?**

**R :** non. Ces adresses sont considérées comme des informations d'identification personnelle et ne sont pas partagées.

**Q : comment puis-je ajouter un contact Windows Live Messenger ayant un ID contenant un domaine autre que ceux pris en charge par Windows Live ?**

**R :** si vous ajoutez un utilisateur Windows Live Messenger avec un compte ou un ID associé à un domaine autre que Windows Live, entrez l'adresse au format suivant : \<nom d'utilisateur\>(\<nom de domaine\>)@msn.com, où \<nom de domaine\> correspond au nom de domaine dans l'adresse de messagerie de l'utilisateur. Par exemple, si vous voulez ajouter ted@contoso.com, vous devez utiliser le format suivant : ted(contoso.com)@msn.com. Pour consulter la liste des domaines administrés par Windows Live, voir la section sur les domaines pris en charge de l'article « Known Issues That Occur with Public Instant Messaging After You Install Live Communications Server Service Pack 1 » (Problèmes connus affectant la messagerie instantanée publique suite à l'installation de Live Communications Server Service Pack 1) à l'adresse http://support.microsoft.com/?kbid=897567.

**Q : combien de temps dure le processus d'approvisionnement ?**

**R :** l'approvisionnement peut prendre jusqu'à 30 jours.

**Q : comment saurais-je que l'approvisionnement est terminé ?**

**R :** Microsoft vous enverra une notification par courrier électronique une fois l'approvisionnement terminé.

**Q : comment puis-je mettre à jour les détails relatifs à la configuration ou de contact que j'envoie ?**

**R :** vous pouvez mettre à jour vos informations sur le même site web que vous avez utilisé pour demander l'approvisionnement, une fois l'approvisionnement terminé. Entrez votre numéro de contrat, puis cliquez sur Mettre à jour le service.

