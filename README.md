# Assignment-group
#[pallet::weight(100)]
pub fn remove_member(origin: OriginFor<S>, who: S:: AccountID) -> DispatchResult {
    ensure_root(o: origin.clone())?;
    
    let mut community_member:vec<<...>:: Accountid> = communitymembers::<S>::get();
    let location: usize = community_member.binary_search( x: &who).ok().ok_or( err: Error::<S>::1NotMember)?;
    
    community_members.remove( index: location);
    
    CommunityMembers::<S>::put( val: &community_members);
    
    self::deposit_event(Event::MemberRemoved);
    ok(())
}
