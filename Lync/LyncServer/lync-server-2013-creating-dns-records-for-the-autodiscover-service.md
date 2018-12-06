---
title: "Lync Server 2013 : Créa. d’enr. DNS pour le service de découverte automatique"
TOCTitle: Création d’enregistrements DNS pour le service de découverte automatique
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690010(v=OCS.15)
ms:contentKeyID: 49296861
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-06-20_

Vos utilisateurs Lync Mobile devront activer la découverte automatique. Une partie de ce processus implique de créer des enregistrements DNS (Domain Name System). Selon vos besoins, il vous faut les éléments suivants :

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles se connectant depuis le réseau de votre organisation.

  - Un enregistrement DNS externe ou public pour prendre en charge les utilisateurs mobiles se connectant depuis Internet.

Et pourquoi pas les deux ? Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS que vous créez peuvent être des enregistrements (hôte) A ou CNAME. Pour vous aider, nous allons voir comment créer ces enregistrements DNS internes et externes ci-dessous. Si vous devez consulter d’autres documents sur les exigences DNS pour les utilisateurs mobiles, vous pouvez vous reporter à [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

## Création d’un enregistrement CNAME DNS interne

1.  Pour créer un enregistrement DNS interne, vous devez vous connecter à un serveur DNS de votre réseau avec un compte de domaine membre du groupe Administrateurs de domaine ou DnsAdmins.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

3.  Dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directe** pour le domaine Active Directory où vos Lync Server 2013pool de directeurs et pool de serveurs frontaux sont installés (par exemple, contoso.local).

4.  Vérifiez si un enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de directeurs dans le cas d’un enregistrement DNS interne ; un enregistrement hôte A doit exister pour le nom de domaine complet (FQDN) des services web internes de votrepool de directeurs (par exemple, lyncwebdir01.contoso.local). S’il ne s’affiche pas, vous ne pourrez pas utiliser de pool de directeurs et devrez employer le FQDN de votre pool de serveurs frontaux, voire un FQDN de serveur unique, si telle est votre configuration.

5.  En tenant compte de ces critères, vérifiez si un enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de serveurs frontaux dans le cas d’un enregistrement DNS interne ; un enregistrement hôte (ou AAAA) doit exister pour le FQDN des services web internes de votre pool de serveurs frontaux (par exemple, lyncwebpool01.contoso.local). Dans le cas contraire, vous devrez relever le FQDN du serveur frontal ou du serveur Standard Edition.

6.  Une fois que vous avez connaissance de l’existence des enregistrements hôte A (ou AAAA), dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)** .

8.  Dans **Nom de l’alias**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.

9.  Dans **Nom de domaine complet (FQDN) pour l’hôte de destination**, entrez ou accédez au FQDN des services web internes de votre pool de directeurs (par exemple, lyncwebdir01.contoso.local), puis cliquez sur **OK**.

10. Vous devez créer un enregistrement CNAME de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

## Création d’un enregistrement CNAME DNS externe

1.  Pour créer un enregistrement CNAME DNS externe, vous devrez vous connecter à votre fournisseur DNS public, puis suivre la procédure décrite. Il est impossible de déterminer votre emplacement exact dans l’environnement du fournisseur DNS, car vous pouvez gérer votre DNS externe de différentes manières. Cependant, nous espérons que cette procédure vous sera utile.

2.  Connectez-vous à votre fournisseur DNS externe avec un compte pouvant créer des enregistrements DNS dans cet environnement.

3.  Vous devez déjà avoir créé un domaine SIP pour cet environnement. Développez **Zone de recherche directe** pour ce domaine SIP ou sélectionnez-le selon l’interface DNS externe utilisée.

4.  Un enregistrement hôte A (AAAA pour IPv6) doit déjà s’afficher pour votre pool de directeurs (comme lyncwebexdir01.contoso.com) ; confirmez cette option. Dans le cas contraire, vous ne pourrez pas utiliser de pool de directeurs. Si tel est le cas, vous devrez employer le FQDN de votre pool frontal ou, si vous effectuez cette opération pour un serveur unique, de votre serveur frontal ou Standard Edition.

5.  Vous devrez également confirmer qu’un enregistrement hôte A (AAAA pour IPv6) existe pour le nom de domaine complet (FQDN) des services web externes de votre pool frontal (comme lyncwebextpool01.contoso.com), ou bien un FQDN pour votre FQDN de serveur unique, si vous ne disposez pas de ce type de pool. Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous ne possédez pas de pool directeur.

6.  À présent, dans le format approprié à votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **Nouvel alias (CNAME)** (il peut s’agir d’une option de menu ou d’un lien selon le format du fournisseur DNS).

7.  Une zone de texte **Nom d’alias** doit s’afficher. Comme pour le DNS interne, vous devez entrer le nom d’hôte correspondant à l’URL de service externe de découverte automatique.

8.  Une zone de texte **Nom de domaine complet (FQDN) pour l’hôte de destination** doit également s’afficher, où vous saisirez le FQDN des services web externes de votre pool de directeurs (par exemple, lyncwebexdir01.contoso.com). Cliquez sur OK ou effectuez n’importe quelle opération sur le DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4 précédente, si vous ne disposez pas d’un pool de directeurs, vous devrez utiliser le FQDN du pool frontal ou le FQDN de serveur unique que vous avez configuré, le cas échéant.

9.  Vous devrez créer un nouvel enregistrement CNAME de découverte automatique dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

## Création d’un enregistrement A DNS interne

1.  Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS de votre réseau avec un compte de domaine membre du groupe Administrateurs de domaine ou DnsAdmins.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **DNS** .

3.  Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directe** pour votre domaine Active Directory (par exemple, contoso.local) où votre pool Lync Server 2013directeur et votre pool de serveurs frontaux sont installés.

4.  Vérifiez si l’enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de directeurs dans le cas d’un enregistrement DNS interne ; un enregistrement hôte A doit exister pour le nom de domaine complet (FQDN) des services web internes pour votre pool de directeurs (par exemple, lyncwebdir01.contoso.local). Dans le cas contraire, vous ne pourrez pas utiliser de pool de directeurs et devrez vous servir de l’adresse IP de votre pool frontal, voire d’une adresse IP de serveur unique, si telle est votre configuration.

5.  En tenant compte de ces critères, vérifiez si un enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de serveurs frontaux dans le cas d’un enregistrement DNS interne ; un enregistrement hôte A (ur AAAA) doit exister pour le FQDN des services web internes pour votre pool de serveurs frontaux (par exemple, lyncwebpool01.contoso.local). Dans le cas contraire vous devrez relever l’adresse IP du serveur frontal or serveur Standard Edition.

6.  Une fois que vous avez connaissance de l’existence des enregistrements hôte A (ou AAAA), dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)** .

8.  Dans **Nom**, saisissez le nom d’hôte correspondant à l’URL du service interne de découverte automatique : lyncdiscoverinternal.

9.  Dans **Adresse IP**, entrez l’adresse IP des services web internes du directeur (ou, si vous utilisez un équilibreur de charge, indiquez l’adresse IP virtuelle (VIP) de celui du directeur). Comme indiqué à l’étape 4 précédente, si vous n’utilisez pas de directeur, vous devrez entrer l’adresse IP du serveur frontal ou du serveur Standard Edition ou, si vous vous servez d’un équilibreur de charge, la VIP de celui du pool de serveurs frontaux.

10. Cliquez sur **Ajouter un hôte** , puis sur **OK** .

11. Pour créer un autre enregistrement A ou AAAA, répétez les étapes 8 à 10 et gardez à l’esprit que vous devrez créer d’autres enregistrements de découverte automatique A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync Server 2013.

12. Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé** .

## Création d’un enregistrement DNS A externe

1.  Pour créer un compte DNS externe, connectez-vous à votre fournisseur DNS public, puis suivez la procédure décrite. Il est impossible de déterminer votre emplacement exact dans l’environnement du fournisseur DNS, car vous pouvez gérer votre DNS externe de différentes manières. Cependant, nous espérons que cette procédure vous sera utile.

2.  Vous devrez vous connecter en tant que compte pouvant créer des enregistrements DNS dans ce domaine.

3.  Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com). Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

4.  Vous devez déjà utiliser un enregistrement hôte A (AAAA pour IPv6) pour votre pool de directeurs (comme lyncwebexdir01.contoso.com) ; confirmez donc cette option et l’adresse IP. Dans le cas contraire, vous ne pourrez pas utiliser de pool de directeurs. Si tel est le cas, vous devrez employer l’adresse IP de votre serveur frontal ou Standard Edition. N’oubliez pas que vos serveurs peuvent se trouver derrière un équilibreur de charge ou utiliser un proxy inverse. Relevez également les adresses IP pour suivre la procédure ci-après.

5.  Vous devrez également confirmer qu’un enregistrement hôte A (AAAA pour IPv6) existe pour le nom de domaine complet (FQDN) des services web externes de votre pool frontal (comme lyncwebextpool01.contoso.com) ou une adresse IP de votre installation Lync de serveur unique si vous ne disposez pas de pool frontal. Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous ne possédez pas de pool directeur.

6.  À présent, dans le format approprié à votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **Nouvel hôte A ou AAAA** (il peut s’agir d’une option de menu ou d’un lien, selon le format du fournisseur DNS).

7.  Une zone permettant d’indiquer un **Nom** doit apparaîre. Entrez le nom d’hôte correspondant à l’URL de service externe de découverte automatique : lyncdiscover.

8.  Une zone de texte **Adresse IP** doit également s’afficher, où vous saisirez l’adresse IP de votre pool de directeurs (par exemple, lyncwebexdir01.contoso.com), voire celle de l’équilibreur de charge de votre pool (ou l’adresse IP d’un proxy inverse y menant), puis cliquerez sur OK ou effectuerez n’importe quelle opération sur le DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4 précédente, si vous ne disposez pas d’un pool de directeurs, vous devrez utiliser l’adresse IP du pool frontal ou du serveur unique que vous avez configurée, le cas échéant.

9.  Vous devrez également créer un nouvel enregistrement de découverte automatique A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

