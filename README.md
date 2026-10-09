# ตาราง GoF Patterns

| Pattern | ปัญหาที่แก้ |ไฟล์/คลาสที่ใช้|
|---|---|---|
|State|การยืมมีหลายสถานะ แต่ละสถานะอนุญาตการทำงานไม่เหมือนกัน เช่น คำขอที่ยังไม่อนุมัติไม่ควรรับหรือคืนอุปกรณ์ จึงแยกกฎของแต่ละสถานะออกจากกัน|`domain/state/BorrowState.java, PendingState.java, ApprovedState.java, BorrowedState.java, OverdueState.java, ReturnedState.java, BorrowStateResolver.java`|
|Strategy|ผู้ยืมแต่ละประเภทอาจมีหลักเกณฑ์คำนวณค่าปรับต่างกัน จึงแยกวิธีคำนวณค่าปรับตามบทบาทออกเป็นกลยุทธ์ และเลือกใช้ให้เหมาะกับผู้ยืม|`service/FineStrategyService.java, service/strategy/StandardFineStrategy.java, VipFineStrategy.java, FineStrategyResolver.java`|
|Observer|เมื่อรายการยืมเกินกำหนด ต้องแจ้งเตือนโดยไม่ให้โค้ดจัดการคำขอยืมต้องรับผิดชอบรายละเอียดการส่งแจ้งเตือนทั้งหมด|`common/event/OverdueEvent.java, OverdueEventListener.java, service/impl/BorrowRequestServiceImpl.java`|
